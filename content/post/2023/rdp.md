---
title: "Remote Desktop Protocol"
published: 2023-12-21T10:06:22+10:00
lastUpdated: 2023-12-21T10:06:22+10:00
url: rdp
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://i.imgur.com/REP8Ksb_d.webp?maxwidth=760&fidelity=grand"
    # alt: "<alt text>"
    caption: "Generated with Microsoft's AI Image Creator"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Homelab # Homelab, Writeup, Personal
tags:
    - 
    - 

draft: true

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's setup Remote Desktop Protocol on Ubuntu.

Start with following [this guide](https://www.digitalocean.com/community/tutorials/how-to-enable-remote-desktop-protocol-using-xrdp-on-ubuntu-22-04).

Make sure you're not logged in as the same user, thanks [to this](https://askubuntu.com/questions/1308551/xrdp-disconnects-immediately-after-correct-credentials).

If you're using a laptop, thanks [to this](https://fostips.com/lid-close-action-ubuntu-21-04-laptop/).
- `sudo nano /etc/systemd/logind.conf`

```asp
HandleSuspendKey=ignore
HandleHibernateKey=ignore
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
```

---

Thanks for reading
