---
title: "Basic Home Network Analysis - Beginner Cyber Sec Project"
author: Mr Ash
type: "post"
published: 2022-02-04
lastUpdated: 2022-11-04
url: "/basic-home-network-analysis-beginner-cyber-sec-project/"
image: https://images.unsplash.com/photo-1563206767-5b18f218e8de?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzMxMzIxMjQ&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1710
categories: Cyber
tags:
    - Networking
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Basic-Home-Network-Analysis--Beginner-Cyber-Sec-Project-e186f3t" width="400px"></iframe> -->

Are you a Cyber Sec student? Or just interested in the Cyber Sec space?

Yes, and yes!

Do you go to family and friends, hop on their network and poke around? It’s easy to do and you can quickly find vulnerabilities that someone could exploit.

Recently, I stayed at my wife’s uncle and aunties house and I noticed a major network vuln.

Imagine you put a lock on a door for home security but never lock it, robbers just come in every night to look around.

It’s very common and easy to spot and fix, let’s go over the steps.

*Disclaimer, the skillset and tools used are intended to protect and secure people and technology. Do not use this knowledge for harm, act in the best interest of others, not yourself.*

## Game Plan

How do you approach a network?

I like to think about this in two ways. One, physically, and two, logically. Physically makes sense, right? The location of computers, phones, modems or routers, printers and other network-connected devices. In my case, I’m in an empty family home, all phones, tablets and portable devices are most likely taken, or, offsite.

Then logically, how are the devices connected? In most home office networks, a single device, the modem-router is connecting the entire network. Therefore it’s a very simple, flat network configuration, this is the case for my family network also.

Next up, keeping a record.

For this network analysis, it’s very, very simple. But it’s a good habit to form of writing down what you do, as you do it. I use Notion to jot everything down, sometimes notepad when I’m in a pinch. But any text editor on any operating system is fine.

## Network Landscape

Okay, let’s get on the network and see what we’re working with.

Now, coming to a family network, you’re most likely a trusted actor, meaning, the wifi password will be given to you voluntarily. If that’s the case, you’re on the network, well done.

If not, you need to gain access. Now you have some options here if you can simply ask, well then yeah, do that and get the password verbally or via message. Otherwise, locate the home modem-router, in most cases the default password located on the physical device will work. This is because not many people change their default wifi password.

In my case, the password was changed to something more secure, well-done family. And the password was given to me directly, yay, I’m trusted.

Great, so you’re on the network in one way or another.

Now let’s get an idea of the logic of the network. What that means is the Internet Protocol (IP) scheme, we want to know how the home modem-router is configured to issue IPs.

IPs is shorthand for IP Addresses, the most common is `192.168.0.1` – it’s a series of numbers that makes your device identifiable on a network. IPs are issued by a Dynamic Host Configuration Protocol (DHCP), this is automatically set up in-home modem routers.

Now we’re on the network, we’ve been given an IP and we can find the IP scheme from that.

Open your terminal emulator of choice, for Windows, either CMD, Powershell or Windows Terminal. On Mac or Linux, open Terminal. Now, for Windows type `ipconfig` and for Mac or Linux, type `ifconfig` – this will show your IP configuration.

Now let’s analyze the output information.

![https://p146.p4.n0.cdn.getcloudapp.com/items/RBuL8peG/d9eed1b7-fa04-4e8b-aba8-46e74986cc82.jpeg?v=0545969022dea48f9ba45080923dade7](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuL8peG/d9eed1b7-fa04-4e8b-aba8-46e74986cc82.jpeg?v=0545969022dea48f9ba45080923dade7)

To explain, you’re looking at a list of network adapters on your computer. Your computer might have one, two or like me, nine. This is physical or virtual hardware responsible for sending and receiving information to and from your computer. It’s one of the pieces on how your computer can connect to the internet.

You’re most likely connected via WiFi to the network, so look for `Wireless LAN adapter WiFi:` however, it might be worded differently. You’ll need to use some critical thinking here.

We’re looking for IPv4, in my case, `192.168.0.31` – so this is my IP address from the modem-router, also known as a gateway. The term gateway under `Connection-specific DNS Suffix` gives away that this is the real device we’re looking for. So, the `Default Gateway` is the IP address of the modem-router, the logical address of how we can access the network!

Oh, the longer gibberish of letters and numbers is also the IP address. Yes, there are two types of IPs, I know, so easy to understand (sarcasm). That’s known as IPv6, we’re just focused on the older, much beloved, still-in-use-today IPv4.

If you have Linux installed, it’s recommended to run a scan using a tool called nmap. If you don’t have Linux, set up [Ubuntu via VirtualBox](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/) or [Kali via WSL](https://mrash.co/kali-linux-wsl-without-microsoft-store/) and for help, see [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/).

`nmap [IP Range]` e.g. `namp 192.168.0.*` – there’s a few ways to write this, but this is easy. We’re telling nmap to scan all IPs between `192.168.0.1` and `192.168.0.255` – see the image below with the number one.

![https://p146.p4.n0.cdn.getcloudapp.com/items/5zuNQlY0/4500a401-a3e0-4695-b137-da0236f58bf1.jpeg?v=af6cec48f84e6ae6d04591736e80fbba](https://p146.p4.n0.cdn.getcloudapp.com/items/5zuNQlY0/4500a401-a3e0-4695-b137-da0236f58bf1.jpeg?v=af6cec48f84e6ae6d04591736e80fbba)

Number 2 on the image shows the ports open. Ports do a lot, but one way to understand them is they organise traffic sent to your computer, it’s how your computer understands the difference between a webpage and an IP address.

Number 3 on the image shows the summary of the nmap scan. In my case, I only have a single host up, so I know going forward that I’m not going to find any other computers or phones on and connected.

## Device Security

All modern home modem-routers have a web server built into them, this makes it easy to set them up giving users a web user interface.

Let’s head over to your browser of choice, Google Chrome, Edge, Safari, Brave… whatever! And navigate to the IP address of the modem router.

In the address bar, simply type the IP for the default gateway we saw earlier, in my case, it’s `192.168.0.1` – this may be the same or similar for you too.

You should be greeted by a login screen, if you see settings, then there’s no login at all, that’s equally as bad as the default login creds. Most default modem-routers use admin/admin as their username and password combination, this should always be changed!

![https://p146.p4.n0.cdn.getcloudapp.com/items/nOuvGy7w/69f4166a-db90-4d3e-a51f-51c3bc3ee51a.jpeg?v=0845131ff92998b203297bab322a48d7](https://p146.p4.n0.cdn.getcloudapp.com/items/nOuvGy7w/69f4166a-db90-4d3e-a51f-51c3bc3ee51a.jpeg?v=0845131ff92998b203297bab322a48d7)

Once you’re in, you can make any changes to the network and see any connected devices.

The WAN or Public IP is issued from the ISP, in this case, it’s Telstra here in Australia. NEVER share this Public IP with anyone, and as you can see, it’s blurred out in the image below.

![https://p146.p4.n0.cdn.getcloudapp.com/items/Wnu0oP9p/e8ce3c92-3213-4e53-938e-8aad21d691a9.jpeg?v=72c691a31aaa0b0eaeda55aca82bbfaf](https://p146.p4.n0.cdn.getcloudapp.com/items/Wnu0oP9p/e8ce3c92-3213-4e53-938e-8aad21d691a9.jpeg?v=72c691a31aaa0b0eaeda55aca82bbfaf)

Something interesting in my case is the list of devices shown on the home modem router. Printer, Smart TV and my computer… but there was a fourth device. Interesting.

My scan from earlier didn’t show that device. So to confirm if this device is up and running is to ping it. Back to Linux or any terminal emulator, run `ping [IP Address]`.

![https://p146.p4.n0.cdn.getcloudapp.com/items/lluorpK6/a33d373b-af2a-4bb5-b399-252adeae81a3.jpeg?v=1d043b7f91320b7086ce0109eaaa8319](https://p146.p4.n0.cdn.getcloudapp.com/items/lluorpK6/a33d373b-af2a-4bb5-b399-252adeae81a3.jpeg?v=1d043b7f91320b7086ce0109eaaa8319)

The ping tool sends small packets (data) from your computer to the target device, if the device is awake and responds, then you’ll see the same or similar information as above.

Somewhere in the house is another device, running and connected to the network. For an attacker, this would be the perfect time to strike, no one is home, the device is easily accessible, it’s a dream situation to start attacking this computer.

## Documentation

Now let’s package all our findings into something someone could understand and action.

This is documentation, it’s not exciting, but it’s very important!

I think about documentation as the bridge between the Cyberworld and the outside world. Well written documentation better protects networks and helps people understand why Cyber Sec helps.

In the case of a family home network, this can be as simple as leaving a note or writing a simple email. The goal of good documentation is to write for your audience, meaning, who is going to be reading it? If it’s someone who doesn’t know a lot about technology, make it easy to understand and DON’T use jargon, i.e. words that only we know in the Cyber Sec world.

Well, that’s it for Basic Home Network Analysis, I hope you enjoyed it.

If you’d like to help shape future articles, I tweet ideas before I write on [Twitter](https://twitter.com/mrash_co/status/1444057444133453826?ref_src=twsrc%5Etfw)

This is Day 20 of [#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.