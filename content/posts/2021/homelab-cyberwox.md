---
title: CyberWox CyberSec Homelab on Virtual Box
author: Mr Ash
type: "post"
published: 2021-08-21
lastUpdated: 2022-11-02
url: "/cyberwox-cybersec-homelab-virtual-box/"
image: /wp-content/uploads/2021/08/pexels-photo-3861969.jpeg
categories:
    - Cyber
tags:
    - Homelab
    - Networking
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/CyberWoxs-Cyber-Sec-Homelab-On-Virtual-Box-e16j8bl" width="400px"></iframe> -->

Homelabs are fun, challenging, but fun.

Building an entire virtual network of interconnected computers to simulate real-world traffic and situations.

This is my additional guide to [Cyberwox’s Building a Cybersecurity Homelab](https://www.cyberwoxacademy.com/post/building-a-cybersecurity-homelab), but, for those using VirtualBox. Here’s a visual guide for the lab:

<iframe height="450" loading="lazy" src="https://whimsical.com/embed/7i8mayV9TtRetih9DFJoEt@2Ux7TurymNKHZLzUBNqw" style="border:none" width="100%"></iframe>

\*Disclaimer, this does not contain 100% of the steps of this project.

## Intro

Ideally, use a dedicated lab computer for this, a spare laptop or an old gaming PC. Spec-wise, 4-8 Core CPU, 16-32Gb RAM, 500Gb+ HDD is recommended.

Let’s get everything you need for the lab. You’ll be downloading an EXE file i.e. an application and some [ISO](https://www.lifewire.com/iso-file-2625923) files, these are disc image files. Start by creating an ‘Image’ folder to store everything in.

Download and install [VirtualBox](https://virtualbox.org/) (VBox), this is the hypervisor we’ll be using to virtually simulate the network. If this is your first time, follow the [User Manual](https://www.virtualbox.org/manual/UserManual.html) provided. If you’re familiar with virtualisation software, feel free to use VMWare or Hyper-V. [Read this](https://appuals.com/fix-virtualbox-not-showing-64-bit-windows-10/) if you’re having VBox issues, it’s worth disabling Hyper-V.

I’m assuming this will all be done on a Windows 10 64-bit desktop.

Get a [pfSense ISO](https://www.pfsense.org/download/) (AMD-64bit), this is the network segmentation, dynamic host control protocol (DHCP) and firewall. Next, download [Security Onion ISO](https://github.com/Security-Onion-Solutions/securityonion/blob/master/VERIFY_ISO.md), this is for intrusion detection system (IDS), monitoring, and logging.

Grab an [Ubunutu Desktop ISO](https://ubuntu.com/download/desktop), an [Ubunutu Server ISO](https://ubuntu.com/download/server) and a [Kali Linux ISO](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/), these are Linux operating systems. Then get a [Windows Server ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019) and [Windows 10 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise).

Lastly, get a license for [Splunk](https://dev.splunk.com/enterprise/), sign up and you’ll (most likely) get a free developer license via email within a day or two.

Something I noticed in the original tutorial, NAT adapters get used, I don’t think this is required. You’ll see below all the network adapter configs for each VM.

## Setup

Open VBox and start creating VMs, use a logical nomenclature, like ‘lab1’ as a suffix e.g. l1-pfs, l1-kali etc. It keeps things organised.

**pfSense (l1-pfs)**

Use the following settings:

- Type: BSD, Version: FreeBSD (64-bit)
- 2Gb RAM, 1 Core CPU, 20Gb HDD
- Adapters (NICs): Adapter 1: Bridged, Adapter 2: Internal, l1-vlan2, Adapter 3: Internal, l1-vlan3, Adapter 4: Internal, l1-vlan4, Adapter 5: Internal, l1-vlan5, Adapter 6: Internal, l1-vlan6.
- IP: 192.168.1.1

You’ll need to add extra NICs, you can add up to 4 using the GUI and 8 in total via CLI. Open CMD/PowerShell/Terminal, navigate to where VBox is installed and edit the NICs. Use the commands below to assist:

- Change directories: `cd C:\Program Files\Oracle\VirtualBox`
- Show VM info: `.\VBoxManage showvminfo l1-pfs`
- Set nic5 to internal: `.\VBoxManage modifyvm l1-pfs --nic5 intnet`
- Set nic5 to l1-vlan: `.\VBoxManage modifyvm l1-pfs --intnet5 l1-vlan`
- Set nic6 to internal: `.\VBoxManage modifyvm l1-pfs --nic6 intnet`
- Set nic6 to l1-vlan: `.\VBoxManage modifyvm l1-pfs --intnet6 l1-vlan`

Once the NICs are turned on, they can be edited via GUI of the VM.

Once you’re done with that, follow the CyberWox tutorial for all the details.

After setup, It’s worth adding in firewall rules for each NIC as you’ll run into problems later. Firewall &gt; Rules &gt; Add &gt; Any Protocols &gt; Save &gt; Apply.

Thanks to [How2Shout](https://www.how2shout.com/how-to/install-pfsense-virtualbox-linux-vmware-player.html) and [SuperUser](https://superuser.com/questions/749978/trouble-setting-up-more-than-4-network-adapters-in-virtualbox-xp-guest).

**Kali (l1-kali)**

- Type: Linux, Version: Red Hat (64-bit).
- Specs: 3Gb RAM, 2 Core CPU, 80Gb HDD.
- NIC: Adapter 1: Internal, l1-vlan2.
- IP: 192.168.1.11, gateway: 192.168.1.1

**Security Onion (l1-secon)**

- Type: Linux, Version: Red Hat (64-bit).
- Specs: 12Gb RAM, 4 Core CPU, 350Gb HDD.
- NICs: Adapter 1: Internal, l1-vlan4, Adapter 2: Internal, l1-vlan5.
- IP: 192.168.3.10, gateway: 192.168.3.1

**Ubuntu (l1-ubd)**

- Type: Linux, Version: Ubuntu (64-bit).
- Specs: 2Gb RAM, 1 Core CPU, 20Gb HDD.
- NICs: Adapter 1: Internal, l1-vlan4.
- IP: 192.168.3.11, gateway: 192.168.3.1

**Splunk (l1-sp)**

- Type: Linux, Version: Debian (64-bit).
- Specs: 4Gb RAM, 2 Core CPU, 100Gb HDD.
- NIC: Adapter 1: Internal, l1-vlan6.
- IP: 192.168.4.10, gateway: 192.168.4.1

To manually set static IP for the Splunk machine:

- Set static IP `sudo ifconfig enp0s8 192.168.4.10 netmask 255.255.255.0`
- Set default gateway `sudo route add default gw 192.168.4.1 enp0s8`

I put the above in a bash script, added a line to execute splunk and then in crontab to automate this every time on startup:

- Create file `nano ip-config`

```bash
#!bin/bash

sudo ifconfig enp0s8 192.168.4.10 netmask 255.255.255.0
sudo route add default gw 192.168.4.1 enp0s8

./home/splunk-admin/Downloads/splunk/bin/splunk start
```

- Make executable `chmod +x ip-config`
- Open Crontab `crontab -e`
- Add at end `@reboot sh /home/splunk-admin/ip-config`
- Reboot `sudo reboot`

Thanks to [ByteFreaks](https://bytefreaks.net/gnulinux/how-to-set-a-static-ip-address-from-the-command-line-in-gnulinux-using-ifconfig-and-route), [LinuxHint](https://linuxhint.com/debian_etc_network_interfaces/), [Ryan](https://ryanstutorials.net/bash-scripting-tutorial/bash-script.php) and [Baeldung](https://www.baeldung.com/linux/run-script-on-startup).

**Windows Server (l1-wsv)**

- Type: Windows, Version: Windows Server 2019
- Specs: 3Gb RAM, 2 Core CPU, 50Gb HDD
- NIC: Adapter 1, Internal, l1-vlan3
- IP: 192.168.2.10, Gateway: 192.168.2.1

**Windows Client 1 and 2 (l1-wc1, l1-wc2)**

- Type: Windows, Version: Windows 10
- Specs: 2Gb RAM, 2 Core CPU, 25Gb HDD
- NIC: Adapter 1, Internal, l1-vlan3
- IP: 192.168.2.11-12, Gateway: 192.168.2.1

This is Day 18 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to follow the journey!

If you have feedback, send me a message [@mrashleyball](https://twitter.com/mrashleyball).

Happy Hacking.