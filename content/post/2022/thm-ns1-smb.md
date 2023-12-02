---
title: TryHackMe Network Services Walkthrough SMB Part 1/3
author: Mr Ash
type: "post"
published: 2022-03-18
lastUpdated: 2022-11-04
url: "/tryhackme-network-services-walkthrough-smb-part-1-3/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/L1uRBW0z/c1ac7086-824b-428c-9b67-bbb382fc9dbc.png?v=8787d496ee28e8e1523a47bd350d9f17
categories: Cyber
tags:
    - Hacking
    - TryHackMe
    - Networking
---

## Task 1 Get Connected

Questions

- Ready? Let’s get going! – No answer needed, carry on.

 Offline checklist to track your learning path, become a great hacker and stay on task.

## Task 2 Understanding SMB

- What does SMB stand for? – Server Message Block
- What type of protocol is SMB? – response-request
- What do clients connect to servers using? – TCP/IP
- What systems does Samba run on? – Unix

## Task 3 Enumerating SMB

Run nmap scan.

![https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxEr8/495d025a-7b15-4222-a6e3-262081ec8fde.jpeg?v=bb76d881e7362c340426d2e881165c95](https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxEr8/495d025a-7b15-4222-a6e3-262081ec8fde.jpeg?v=bb76d881e7362c340426d2e881165c95)

Run enum4linux scan.

![https://p146.p4.n0.cdn.getcloudapp.com/items/04uEgZ65/94fdb523-85de-4da8-9826-ee0c0ea16a59.jpeg?v=4b3296ecd8899cd8c492ce3c7b780b86](https://p146.p4.n0.cdn.getcloudapp.com/items/04uEgZ65/94fdb523-85de-4da8-9826-ee0c0ea16a59.jpeg?v=4b3296ecd8899cd8c492ce3c7b780b86)

Questions:

- Conduct an nmap scan of your choosing, How many ports are open? – 3
- What ports is SMB running on? – 139/445
- Let’s get started with Enum4Linux, conduct a full basic enumeration. For starters, what is the workgroup name? – WORKGROUP
- What comes up as the name of the machine? – POLOSMB
- What operating system version is running? – 6.1
- What share sticks out as something we might want to investigate? – profiles

## Task 4 Exploiting SMB

Connect using `smbclient`:

![https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRmOLm/20eec8de-89e3-46f2-80dc-3b6d27a502dd.jpeg?v=c5caa032c750d46dee0f6cfce1bf3eef](https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRmOLm/20eec8de-89e3-46f2-80dc-3b6d27a502dd.jpeg?v=c5caa032c750d46dee0f6cfce1bf3eef)

Use the `more` command, don’t forget the quotations!

![https://p146.p4.n0.cdn.getcloudapp.com/items/lluE4lXW/070fe98c-60c8-4ad7-8bef-7a67e5216491.jpeg?v=9f8f1ed689e003f3350774456a5015a0](https://p146.p4.n0.cdn.getcloudapp.com/items/lluE4lXW/070fe98c-60c8-4ad7-8bef-7a67e5216491.jpeg?v=9f8f1ed689e003f3350774456a5015a0)

Use `get` to copy the `id_rsa` file from the server to your machine:

![https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxERj/9a8b619c-e617-48f4-a2c5-8036f4685d7e.jpeg?v=852578264d21f58d80460ee97014e6ed](https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxERj/9a8b619c-e617-48f4-a2c5-8036f4685d7e.jpeg?v=852578264d21f58d80460ee97014e6ed)

Questions:

- What would be the correct syntax to access an SMB share called “secret” as user “suit” on a machine with the IP 10.10.10.2 on the default port? – smbclient [//10.10.10.2/secret](//10.10.10.2/secret) -U suit -p 445
- Great! Now you’ve got a hang of the syntax, let’s have a go at trying to exploit this vulnerability. You have a list of users, the name of the share (smb) and a suspected vulnerability. – No answer needed.
- Does the share allow anonymous access? Y/N? – Y
- Great! Have a look around for any interesting documents that could contain valuable information. Who can we assume this profile folder belongs to? – John Cactus
- What service has been configured to allow him to work from home? – ssh
- Okay! Now we know this, what directory on the share should we look in? – .ssh
- This directory contains authentication keys that allow a user to authenticate themselves on, and then access, a server. Which of these keys is most useful to us? – id\_rsa
- What is the smb.txt flag? – THM{\*\*\*\*\*\*\*\*\*\*\*}

{{<youtube DwPuDptnc2w>}}

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/?feature=oembed" title="TryHackMe Network Services 1 Part 1 SMB • Walkthrough" width="800"></iframe></div>

 -->

This is Day 40 of [#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, follow the [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.