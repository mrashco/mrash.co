---
title: "Homelabs \u2022 Beginner&#8217;s Guide To Homelabbing"
author: Mr Ash
type: "post"
published: 2021-11-07
lastUpdated: 2022-11-04
url: "/homelabs-beginners-guide-to-homelabbing/"
image: https://images.unsplash.com/flagged/photo-1579274216947-86eaa4b00475?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzYyNzM2OTg&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=1440&h=2560
categories: Cyber 
tags:
    - Homelab
    - Networking
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Homelabs--Beginners-Guide-To-Homelabbing-e19st0r" width="400px"></iframe> -->

You are probably new to homelabbing and need a bit of guidance. Building a homelab means building a computer network, or lab, at home.

Homelabs can be anything from old laptops to expensive high-end enterprise equipment.

Typically, you’ll find homelabs involve a lot of virtual computers, meaning they’re not physical. There’s little entry to get started and unlimited possibility as your homelab grows.

You’ll find techies and sys-admins from all over the world who love to share their homelabs, projects and builds. I’ll share my homelabbing journey a bit later.

*Disclaimer, this is not a technical step-by-step set-up for your homelab. Rather, an overview for motivation and inspiration purposes.*

## Why Build A Homelab?

Homelabs let you learn enterprise equipment and software in the comfort of your own house.

If you’re in the industry, homelabbing keeps you current, or maybe you want to get into IT, or you might love computing and want to learn more. Regardless of the reason, welcome to the ever-expanding world of homelabs.

Labs, for short, are largely used for experimentation before rolling stuff into a production environment, learning and/or practice involving all of the above plus much more. They’re fun. They’re expensive. They’re a hobby. Ultimately, for most people, a homelab is a plaything that occasionally gets out of hand.

For a real-life example, [Darknet Diaries Episode 47](https://darknetdiaries.com/episode/47/) has a cyber security analyst mention their homelab which helped to kick-start their career.

## Getting Started With Homelabs

For the best guide to Homelabbing, head over to [r/homelab](https://www.reddit.com/r/homelab/) and see the [wiki](https://www.reddit.com/r/homelab/wiki/index).

The community is helpful and the guides are great! Search the subreddit before asking questions, there’s years worth of topics so yours has most likely been discussed before.

For an extensive list of resources, see [reswob10/HomeLabResources](https://github.com/reswob10/HomeLabResources).

Here’s a quick list of what I recommend:

- **Reason(s):** figure out why you want to get into homelabbing, is it for fun or a job?
- **Plan:** then put a rough list together of what you need and want.
- **Aquire:** get what you need to start, use what you have, ask around or buy.

Remember to start small and simple, don’t get FOMO or think you need ‘the best gear’ to setup your homelab. Start with what you have and enjoy the journey.

## Share Your Homelab: Buildlog 2021

Head back to the subreddit r/homelab to get some inspiration, here’s what mine looks like.

**Hardware/Devices**

- Default ISP Modem/Router, Asus Wifi Extenders x2.
- Server 0 (sv0): i5 4th Gen, 32Gb DDR3, HDDx4 total 2.5Tb, Dual Ethernet.
- Server 1 (sv1): i5 3rd Gen, 32Gb DDR3, HDDx4 total 3.1Tb, Dual Ethernet, Wifi.
- Raspberry Pi 3 Model B+ (pi1): 1.4GHz 4 Core, 1Gb, 64Gb SD, Ethernet, Wifi.

**Software**

- sv0: Proxmox.
- sv1: Windows Server 2019, VirtualBox, Plex.
- pi1: Rasbian.

**Usecases:**

- sv0: Virtual Routing (pfSense), Docker Containers.
- sv1: Virtual Sandbox ([vLAN1](https://mrash.co/cyberwox-cybersec-homelab-virtual-box/)), Media Server.
- pi1: Pihole, Custom Python Scripts.

My homelab is for fun and professional development. I started with my brother-in-law’s old gaming PC and have built it up from there. All up, I’ve spent about $200 on second-hand parts.

I’ve got a lot of plans for services and self-hosted options I want to explore. Docker containers running monitoring software, virtual routing and tracking network-connected devices, custom python programs and so much more.

Homelabbing is the nerds equivalent of home improvement, and I love it.

Enjoy homelabbing and I’ll see you in the subreddit!

This is Day 28 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.