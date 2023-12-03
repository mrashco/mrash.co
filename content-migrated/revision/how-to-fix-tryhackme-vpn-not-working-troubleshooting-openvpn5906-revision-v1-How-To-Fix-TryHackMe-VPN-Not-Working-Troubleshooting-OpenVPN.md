---
id: 5912
title: How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5912
url: "/?p=5912"
---

Is your TryHackMe OpenVPN not working?

Let’s fix it, here’s what you’ll need:

- Some computer networking knowledge.
- A [TryHackMe](https://tryhackme.com/) account.
- An OpenVPN config file via [Network Access](https://tryhackme.com/access).

Alright, so your there’s a few problems when trying to connect with OpenVPN to TryHackMe. Let’s cover them and learn how to fix connection problems in TryHackMe, let’s go.

## How Do I Use OpenVPN On TryHackMe?

First you need to have an active account with an OpenVPN config file generated and downloaded to your system. You can use any Operating System such as Windows, macOS or Linux with OpenVPN and TryHackMe. This guide will focus on using a [Linux Virtual Machine within Windows](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/), so let’s answer how to connect to OpenVPN?

1. Download your `.ovpn` config file via [Network Access](https://tryhackme.com/access).
2. Select generate, then download config file. ![https://p146.p4.n0.cdn.getcloudapp.com/items/kpuWZA91/9bf78dd7-c115-4e2c-8246-8868c7ec4497.jpg?source=viewer&v=ff6a6070e81c97712fda6fbff27af118](https://p146.p4.n0.cdn.getcloudapp.com/items/kpuWZA91/9bf78dd7-c115-4e2c-8246-8868c7ec4497.jpg?source=viewer&v=ff6a6070e81c97712fda6fbff27af118)
3. Open terminal and run `sudo openvpn path/to/<username>.ovpn`, change `path/to/` to actual path for example `Downloads/hacker101.ovpn`. ![https://p146.p4.n0.cdn.getcloudapp.com/items/9Zug9yR6/cff15de4-1e6d-40a3-95aa-d7ac21ae55d0.jpg?source=viewer&v=3c79ca7fdc13c0610e7fbdcf8e163df2](https://p146.p4.n0.cdn.getcloudapp.com/items/9Zug9yR6/cff15de4-1e6d-40a3-95aa-d7ac21ae55d0.jpg?source=viewer&v=3c79ca7fdc13c0610e7fbdcf8e163df2)
4. After a few seconds, you should see ‘initialization sequence completed’. ![https://p146.p4.n0.cdn.getcloudapp.com/items/qGuxb6OB/f4cccbaa-0637-4ce6-9636-bb76868b5415.jpg?source=viewer&v=5de176c41481a75f4bce193ffd12e2e7](https://p146.p4.n0.cdn.getcloudapp.com/items/qGuxb6OB/f4cccbaa-0637-4ce6-9636-bb76868b5415.jpg?source=viewer&v=5de176c41481a75f4bce193ffd12e2e7)
5. To confirm access, open a new tab in your terminal with `CTRL + SHIFT + T`, run `ifconfig` a ![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQ9W9z/c42f6b08-64c7-4bde-9a03-5b3fc1094055.jpg?source=viewer&v=f19b3809ec0ea721ebef42037be9fcd1](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQ9W9z/c42f6b08-64c7-4bde-9a03-5b3fc1094055.jpg?source=viewer&v=f19b3809ec0ea721ebef42037be9fcd1)
6. To triple confirm, run `ping 10.10.10.10` and check for a response back. This is TryHackMe’s server speifcally made for testing connections. ![https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZAJB4/19345b34-38a1-4622-b74b-4e4cf38864b2.jpg?source=viewer&v=66cc3342c26e5b8c6e94c50035be6897](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZAJB4/19345b34-38a1-4622-b74b-4e4cf38864b2.jpg?source=viewer&v=66cc3342c26e5b8c6e94c50035be6897)
7. And to quadiple check, go back to Network Access and refresh the OpenVPN Access Details section. ![https://p146.p4.n0.cdn.getcloudapp.com/items/nOub72y7/3fb70e69-6989-4ebf-a41d-1fcbdf1cba02.jpeg?v=6a0ae9ed180e8dea0c7836ec0c3a1360](https://p146.p4.n0.cdn.getcloudapp.com/items/nOub72y7/3fb70e69-6989-4ebf-a41d-1fcbdf1cba02.jpeg?v=6a0ae9ed180e8dea0c7836ec0c3a1360)

Great, know you know the answer to ‘How Do I Use OpenVPN On TryHackMe?’ – I hope this has helped you. Continue readying for more information around questions such as ‘Do You Need a VPN For TryHackMe?’ and ‘Why Is TryHackMe Not Working?’

Also, sidenote, when you’re up and running, if you want run OpenVPN in the background, use`sudo openvpn --daemon *.ovpn`.

## Do You Need a VPN For TryHackMe?

No, you don’t need a VPN for TryHackMe to play **all** rooms. But you do need a VPN for TryHackMe for rooms that include systems or Virtual Machines for you to interact with. It’s recommended to use a VPN for TryHackMe as you can then play any room as intended.

Some rooms require downloading files and some open websites within the TryHackMe room. So again no, you don’t need a VPN for **all** TryHackMe rooms. However, if you can in a good habit of using TryHackMe’s VPN, then you can connect to any room.

## Why Is TryHackMe Not Working?

Start with [TryHackMe’s OpenVpn Troubleshooting doc](https://docs.tryhackme.com/docs/openvpn/troubleshooting/openvpn-troubleshooting/) to gain a better idea of what’s not working. It could be openvpn not connecting, here’s a commands to try `sudo ip link set dev tun0 mtu 1200`.

Prehaps your TryHackMe failed to connect to server, try visiting [TryHackMe’s OpenVPN Troubleshooting Git Repo](https://github.com/tryhackme/openvpn-troubleshooting).

- `wget https://raw.githubusercontent.com/tryhackme/openvpn-troubleshooting/master/thm-troubleshoot`
- `chmod +x thm-troubleshoot`
- `./thm-troubleshoot`

If you’re still having issues, make sure you only have a single OpenVPN connection, use `ifconfig` to see your network adapters. OpenVPN will open a tunnel which looks like `tun0` for example. If you see more adapters like `tun1`, `tun2`, then you want to pull those down.

- `sudo ifconfig tun1 down`

Lastly, if you’re running OpenVPN and seeing an OPTIONS ERROR: failed to negotiate cipher with server error. Try running `sed -i 's/cipher AES-256-CBC/data-ciphers AES-256-CBC/' *.ovpn` in the directory of your `ovpn` config file.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuxoJ5x/6a47fb40-0717-4868-a917-dc656d9bd1b7.jpeg?v=58a43a1bf60c4880815abb140a3393b3](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuxoJ5x/6a47fb40-0717-4868-a917-dc656d9bd1b7.jpeg?v=58a43a1bf60c4880815abb140a3393b3)</figure>