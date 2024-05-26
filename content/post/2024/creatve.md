---
title: "Creative"
published: 2024-05-26T17:13:48+10:00
# lastUpdated: 2024-05-26T17:13:48+10:00
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
categories: writeup # Homelab, Writeup, Personal
tags:
    - tryhackme
    - 

draft: true

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---


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
