---
title: "Enumeration"
# published: 2024-05-25T16:44:21+10:00
# lastUpdated: 2024-05-25T16:44:21+10:00
url: enum
alias: # aliases for multiple
    - 
    - 

cover:
    # image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: note # letter, note, page
categories: enum # Homelab, Writeup, Personal
tags:
    - enumeration
    - recon
    - linux enum
    - windows enum

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

rustscan

- `rustscan -a $ip -g`
- `rustscan -a $ip -p $ports -- -sC -sV | tee scan.init`

nmap 

- `nmap -vv -Pn $ip`
- `nmap -vv -Pn -p $ports -A $ip`

feroxbuster

- `feroxbuster -u http://$ipa -w $wordlist | tee fuzz.init`

FFUF

- `ffuf -u http://$ip/FUZZ -w $wordlist | tee fuzz.init`

firefox

- Analysis: Whatruns, Wappalyzer
- `/robots.txt`, `sitemap(.xml)`

smb

- `enum4linux $ipa | tee enum4.txt` # smb shares

Linux Enumeration

- `ls -la /home`
- `cat /etc/passwd`
- `cat /etc/crontab`
- `sudo -l` # run sudo with?
- `find / —perm 4000 2>/dev/null` # find suids
- `find / -user $user 2>/dev/null` # find user files
- `find / -name *id_rsa* 2>/dev/null` # find files that match id_rsa

---

Thanks for reading
