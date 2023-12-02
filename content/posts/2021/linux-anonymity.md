---
title: Hackers Beginner Guide To Online Anonymity
author: Mr Ash
type: post
published: 2021-05-21
lastUpdated: 2022-11-02
url: "/hackers-beginner-guide-to-online-anonymity/"

image: https://p146.p4.n0.cdn.getcloudapp.com/items/nOubxrjR/c906d962-1817-457c-be13-769207ae7c27.jpeg?v=5bba9db8ac60e028ca814a0ecff40bfa

categories: 
    - Cyber
tags:
    - 100DaysOfHacking
    - TOR
---

How do we start using our mad hacker skills in the real world AND remain undetected?

We need to set ourselves up to be anonymous! No, we’re not joining a hacktivist group here.

Let’s learn the basics to cover ourselves online. We’ll be using Kali Linux in this example, [here’s my guide](https://mrash.co/kali-linux-wsl-without-microsoft-store/) if you need help getting set up.

For a wider approach to online anonymity, see Kalle Hallden’s [Become Invisible Online](https://youtu.be/S4E4yAktjug).

## Spoofing an IP Address with `anonsurf`

IP or Internet Protocol addresses are one element that makes sending and receiving data possible via our global internet infrastructure.

It gives a (somewhat) unique address that looks like `192.168.1.101` which makes identifying your device possible.

The term IP spoofing, defined as “deception or ruse” means to trick or change your unique address for other devices.

Ready to deceive devices? Ruse the robots?

Before we do, get your current [Public IP](https://whatismyipaddress.com/), this is the real unique address for your home router. It’s how your ISP (Internet Service Provider) connects you to the larger internet infrastructure.

\*Do not share your real Public IP with anyone, EVER!

Let’s go!

We’ll use `git`, version control software, to clone a repo (folder) to our desktop, so `ls` there.

Make sure it’s installed by running `git --help`, if nothing’s there, then `sudo apt install git` on your Linux machine to get it.

Now let’s grab [Anonsurf](https://linuxhint.com/anonsurf/) which “provides users with system-wide anonymization”, awesome!

Setup is simple:

1. Clone: `git clone https://github.com/Und3rf10w/kali-anonsurf.git`
2. Install: `cd kali-anonsurf` `chmod +x installer.sh` `sudo ./installer.sh`
3. Use: `anonsurf start` or `sudo anonsurf start`

That’s it! How cool is that? Test your Public IP again and you’ll notice it’s changed.

Meaning, other devices we use to connect to web services don’t know where we are. I live in Australia, but any web server my computer visits tells them I’m in Germany. Cool!

## Spoofing a MAC Address with `macchanger`

The [MAC (Media Access Control) address](https://en.wikipedia.org/wiki/MAC_address) is another important element that makes our devices talk to each other. Think of this as a more ‘burnt in’ type of IP Address, a bit loose, but just go with it for now.

It’s assigned to a NIC (Network Interface Card) from the manufacturer/vendor i.e. Apple, Intel etc. It looks like `08:02:07:a2:a3:f6`, a bit different to the IP Address from earlier.

We already know what spoofing means, so are you ready to try it?

Awesome!

We’ll use a tool called [MAC Changer](https://www.hacknos.com/macchanger-in-kali-linux/) which can view and change MAC’s for NIC’s… aren’t acronyms fun?

To get your NIC name, use `ifconfig`, it might be `eth0` or something similar.

Easy setup in your terminal emulator:

1. Install: `sudo apt install macchanger`
2. Use: `macchanger --help`
    1. Show: `sudo macchanger -s <nic>`
    2. Random: `sudo macchanger -r <nic>`
    3. Reset: `sudo macchanger -p <nic>`

See the `help or man` pages for more options like setting a manual MAC Address or changing only the Vendor section.

There’s a lot of flexibility that comes with this tool! If you wanted to emulate a specific device from Apple for example use `-l` to see a full list of Vendors.

Be aware you can’t change your mac address permanently, so when you reboot your machine you’ll need to change your MAC address again.

## Setup a Proxychain

When you think of a large metal chain or a small silver one, it’s an interconnected series of rings that form it, right?

A Proxychain is similar, but instead of a series of rings, it’s a series of servers.

When you visit `google.com` there are a few steps for your device to get there but think about it as a fairly direct route.

A Proxy will send your request to `google.com` through another server as a secure means.

So a Proxychain essentially sends your request through a series of other servers before it reaches `google.com`

If that doesn’t make a whole lot of sense, just picture a hidden bridge only we know about, yeah that’s our Proxychain.

Okay! Enough expo, let’s go.

We’ll be using a tool appropriately named `proxychains`.

Setup for `proxychain` is a bit more detailed, but not too bad once you’ve done it.

Follow these steps:

1. Install TOR: `sudo apt install tor`
2. Install Proxy Chains: `sudo apt install proxychains`
3. Edit config file: `sudo nano /etc/proxychains.conf` use the arrow keys to navigate.
    1. Remove `#` next to `dynamic_chain`
    2. Add `#` to `strict_chain`
    3. Add `#` to `proxy_dns`
    4. At the end of file, add `socks5 127.0.0.1 9050`
    5. Close file with `CTRL + X` then `Y` and `ENTER`
4. Run TOR: `sudo service tor start && service tor status`
5. Use Proxy Chains: `proxychains <command>`

You can now send any tool through a tor proxy chain, pretty cool!

## Automate The Process

So now we’ve set up each area to make ourselves more anonymous online, it’s time to automate this setup.

Why? Well, every time we boot our machine, we don’t want to set each service up again! Let’s make a [simple BASH script](https://www.linux.com/training-tutorials/writing-simple-bash-script/) to do this for us.

First, let’s create the file with `nano auto-stealth` and then we’ll add in the following text:

```bash
#!/bin/bash

sudo service tor start

sudo anonsurf start

sudo macchanger -r eth0
```

Save and exit that file using `CTRL + X` then `Y` and `ENTER`.

Lastly, make it executable by using `chmod +x auto-stealth`. Now it’s good to go! Run your BASH Script by simply entering `./auto-stealth` and wella!

How cool is that?

Now every time you want to go full Mr Robot mode, just simply run that one file and BAM! You’re in the matrix.

\*You’ll still have to use `proxychains` before any other command for it to route via the TOR setup, but it’s up and running!

Thanks for reading this guide toward your hacker dreams.

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 10 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.