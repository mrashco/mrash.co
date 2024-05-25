---
title: "Checklist"
# published: 2024-05-26T07:40:09+10:00
# lastUpdated: 2024-05-26T07:40:09+10:00
url: checklist
alias: # aliases for multiple
    - 
    - 

cover:
    #image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: note # letter, note, page
categories: Homelab # Homelab, Writeup, Personal
tags:
    - 
    - 

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Quick guide for pentest CTFs like Boot2Roots.

Links
- [AppSecExplained](https://appsecexplained.gitbook.io/appsecexplained)
- [HackTricks](https://book.hacktricks.xyz/)

## Enumerate
- Open ports? [rustscan](https://mrash.co/rustscan), nmap.
- Running services? 
- Version numbers?
- Operating System (Linux/Windows)?
- Domains? `/etc/hosts`
- Webserver (Apache/Ngnix)?
- Subdomins?

### DNS
- `nslookup $domain`
- `dig -query=ANY $domain`

### Common Files
- robots.txt
- sitemap.xml
- .htaccess
- security.txt
- manifest.json
- browserconfig.xml
- etc



---

Thanks for reading
