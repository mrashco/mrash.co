---
title: "Creative"
published: 2024-05-27T16:42:31+10:00
# lastUpdated: 2024-05-27T16:42:31+10:00
url: creative
alias: # aliases for multiple
    - tryhackme-creative-writeup
    - 

cover:
    # image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Writeup # Homelab, Writeup, Personal
tags:
    - 
    - 

draft: true

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's get creative!

Here's my writeup for the TryHackMe challenge, [Creative](https://tryhackme.com/r/room/creative).

## The Challenge

A simple description **Exploit a vulnerable web application and some misconfigurations to gain root privileges.**

And two flags like usual, user and root.

Okay, let's get into it.

## Enumeration

We know we're starting with a **web application**.

But like usual, let's scan for open ports and services.

Quick rustscan shows SSH on 22, and HTTP on port 80.

![Rustscan Results](https://i.imgur.com/JprfYUT.png)

So let's open `firefox $ip &` to see what we're working with.

Ah, a domain. So `sudo echo $ip creative.thm >> /etc/hosts` to get that working.

Looks like a basic boiler plate html/css template, nothing special.

![](https://i.imgur.com/2l8UADv.jpeg)

Wappalyzer shows Ubuntu and Ngnix running.

After spending sometime looking through the source, nothing is showing.

A quick directory fuzz `ffuf -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -u http://creative.thm/FUZZ` shows `/assets`.

But with a **403**, no luck here.

And with no other common files such as **robots.txt** etc. it's not looking great.

So what's next?

Let's try VHost fuzzing.

`ffuf -H "Host: FUZZ.creative.thm" -c -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u http://creative.thm`

To try

- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
  - `<script> alert("XSS");</script>`
- Local File Inclusion (LFI)
- Remote File Inclusion (RFI)
- **Server-Side Request Forgery (SSRF)**
- Directory Traversal
- Command Injection

http://example.com/<script> alert("XSS");</script> # Made it hang for a while

curl 'http://beta.creative.thm/' -X HEAD -H 'Content-Type: application/x-www-form-urlencoded' --data-raw 'url=""'

curl 'http://beta.creative.thm/' -I

Quick reverse connection test
- `<img src="http://$YOUR_IP/" />`
- `nc -lnvp 80`

---

Thanks for reading
