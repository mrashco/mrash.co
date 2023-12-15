---
title: "Kali"
published: 2023-12-15T19:53:10+10:00
lastUpdated: 2023-12-15T19:53:10+10:00
url: kali
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

Here's my notes for setting up my new Kali Linux Rolling via WSL.

1. Powershell (PSH): `wsl --install`
2. PSH: `winget install kalilinux.kalilinux`
3. Terminal: `CTRL + SHIFT + 4`

Noticed ping doesn't work, so fixed it with [the following](https://superuser.com/questions/288521/problem-with-ping-open-socket-operation-not-permitted): `sysctl -w net.ipv4.ping_group_range="0 1000"`