---
title: "Syncthing"
published: 2023-12-22T06:18:12+10:00
lastUpdated: 2023-12-22T06:18:12+10:00
url: syncthing
alias: # aliases for multiple
    - 
    - 

cover:
    image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Homelab # Homelab, Writeup, Personal
tags:
    - syncthing
    - homelab

draft: true

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's install syncthing on Windows. Open Terminal > type `winget install synctrayzor`.

This is a [standalone app](https://github.com/canton7/SyncTrayzor) that just makes using syncthing more user friendly.

Synctrayzor should be in your taskbar, click it to open the GUI.

Go to Actions > Settings > Connections > Untick 'Global Discovery' and 'Enable Relaying'.

---

Thanks for reading
