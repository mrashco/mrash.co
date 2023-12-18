---
title: "Pi-Hole"
published: 2023-12-18T12:09:01+10:00
lastUpdated: 2023-12-18T12:09:01+10:00
url: pihole
alias: # aliases for multiple
    - 
    - 

cover:
    image: https://images.unsplash.com/photo-1553406830-1c853b38df08?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
    # alt: "<alt text>"
    caption: 'Photo by <a href="https://unsplash.com/@harrisonbroadbent?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Harrison Broadbent</a> on <a href="https://unsplash.com/photos/green-circuit-board-RNqs_Ve8qAo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>'
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # Options: post, letter, note, page
categories: Setup # Options: Writeup, Personal
tags:
    - pihole
    - docker
    - "how to"

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's setup Pi-Hole in Docker, following the [official documentation](https://docs.docker.com/engine/install/raspberry-pi-os/).

- `getconf LONG_BIT` check for 32bit or 64bit. 
- `cat /etc/os-release` check the version of the OS.

After following the installation guide, you might receive these errors:

```plain
E: Package 'docker-ce' has no installation candidate
E: Unable to locate package docker-ce-cli
E: Unable to locate package containerd.io
E: Couldn't find any package by glob 'containerd.io'
E: Couldn't find any package by regex 'containerd.io'
E: Unable to locate package docker-buildx-plugin
E: Unable to locate package docker-compose-**plugin**
```

Switch over to [this guide](https://docs.docker.com/engine/install/raspberry-pi-os/) to manually install docker with the deb files.

- Download all five deb files, get the latest versions.
- `sudo dpkg -i *` to install all five deb files.
- `sudo service docker start && sudo docker run hello-world` to make sure it's working.

Now Docker's installed, let's get a container of Pi-Hole setup [following this](https://github.com/pi-hole/docker-pi-hole).

- `mkdir pihole` and `cd pihole && touch docker-compose.yml`, copy paste the example.
- Adjust ports, TZ and cap_add if you're not using DHCP.
- `sudo docker compose up -d` and
- Check the ports worked with `sudo docker ps` under the ports column or `sudo docker port $containerID`.
  
If there's no ports mapped, check the logs `sudo docker logs -f $containerID`

Looks like the container is always restarting.

You might be having a known issue with [libseccomp2 v2.3.3-4](https://github.com/pi-hole/docker-pi-hole/issues/1194).

[This](https://docs.linuxserver.io/FAQ/#symptoms) shows a short-term fix which works.

Add the following to your docker-compose.yml file.

```yml
security_opt:
    - seccomp=unconfined
```

Then stop, remove and recompose Pi-Hole. 

- `sudo docker stop $containerID`
- `sudo docker rm $containerID`
- Rerun `sudo docker compose up -d` and `sudo docker ps` to check.

Run `sudo netstat -ntlp` to see a list of ports and services.

If you're still having issues, [see here](https://blog.samcater.com/fix-workaround-rpi4-docker-libseccomp2-docker-20/) for another option.

To set the web interface password `sudo docker exec -it $containerID pihole -a -p`

## Update Router

To get your modem/router to use Pi-Hole, update your router settings.

Find the IP of your router (default gateway). On linux `ifconfig`, `ip a` or `ipconfig` on Windows.

Go to the web dashboard http://$routerIP/ and search for LAN. The name may differ for your router.

Update the DNS or nameserver to the IP of your Pi-Hole system.

Now you should start to see queries! Head over to YouTube and watch those ads disappear!

# Can't SSH after installing Pi-Hole

Next issue, can't ssh back into the system running Pi-Hole?

Check what services and ports are exposed with `nmap -Pn $ip` from another system.

Can you see SSH? If not, then it's disabled.

On your system with Pi-Hole:
- `sudo apt install ufw` to install an easier interface for the firewall.
- `sudo ufw allow ssh` to allow ssh connections

## Warning: no upstream servers configured

If you see "warning: no upstream servers configured", go to Settings > DNS.

Select whatever IPv4 and IPv6 Upstream DNS Servers you want like Google or OpenDNS.