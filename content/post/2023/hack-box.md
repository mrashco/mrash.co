---
title: "Hack Box"
published: 2023-12-15T19:53:10+10:00
lastUpdated: 2023-12-15T19:53:10+10:00
url: hack-box
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://images.unsplash.com/photo-1549605659-32d82da3a059?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    # alt: "<alt text>"
    caption: Photo by <a href="https://unsplash.com/@hidd3n?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Kevin Horvat</a> on <a href="https://unsplash.com/photos/flat-screen-monitor-turned-on-Pyjp2zmxuLk?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # Options: , letter, note, page
categories: Setup # Options: Writeup, Personal
tags:
    - kali
    - setup
    - wsl

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's setup a new "Hack Box" for TryHackMe challenges and Capture The Flags (CTFs). 

Previously, I've always used Kali Rolling inside of VirtualBox. But let's try and get away from Virtual Machines (VMs).

Why? Mainly the boot times, slow browsing and general laggy annoyances.

I want a fast, simple system without the need to boot a VM and deal with stutters.

The thinking is, use Windows Subset for Linux (WSL) with headless Kali Linux. Meaning, no Graphical User Interface (GUI). 

For any GUI needs, regular ol' Windows is good for that (hopefully).

## Installation

Here's how to install Kali Linux WSL on Windows.

Open Terminal and use the following commands:
- `wsl --install`
- `wsl --update`
- `wsl --install --distribution kali-linux`

Then in Terminal, use `CTRL + SHIFT + 4 or 5` to open Kali Linux WSL.

Once in, run `sudo apt update -y && sudo apt upgrade -y` for latest updates.

Since Kali Linux WSL by default is barebones. Run `sudo apt install -y kali-linux-headless` for the default install without GUI [metapackge](https://www.kali.org/docs/general-use/metapackages/).

## Setup

Settings `CTRL + ,` > Kali > Additional settings > Appearance. I change the Color scheme, Font size, Retro terminal effects, and Background opacity to 75%.

- `wordlists`, then `Y` to extract rockyou.txt. And `sudo rm rockyou.txt.gz` to remove the gzip file.

## Troubleshooting

If there's any issues, go back and follow the [WSL Documentation Quick Method](https://www.kali.org/docs/wsl/wsl-preparations/).

Don't install Kali with `winget install kali-linux`, it didn't work for me.

If you have more issues, here's some ideas:
- Kali Linux not working: `wsl --unregister kali-linux` and `wsl --install --distribution kali-linux` again.
- ping socket operation not permitted: `sysctl -w net.ipv4.ping_group_range="0 1000"` thanks to [Super User](https://superuser.com/questions/288521/problem-with-ping-open-socket-operation-not-permitted).
- apt signature errors: `echo 'deb https://http.kali.org/kali kali-rolling main non-free contrib' >> /etc/apt/sources.list` thanks to [Linux Config](https://linuxconfig.org/kali-linux-failed-to-fetch-inrelease-repository-fix).

## Conclusion

I ran into a few errors installing headless Kali Linux via WSL. But once I retraced my steps, it was painless.

Now these days Microsoft plays nicely with Linux, it makes the gap between Operating Systems (OSs) very thin.