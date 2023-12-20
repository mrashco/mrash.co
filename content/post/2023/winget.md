---
title: "Winget"
published: 2023-12-20T11:06:47+10:00
lastUpdated: 2023-12-20T11:06:47+10:00
url: winget
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://images.unsplash.com/photo-1642176849879-92f85770f212?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    # alt: "<alt text>"
    caption: 'Photo by <a href="https://unsplash.com/@sunriseking?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Sunrise King</a> on <a href="https://unsplash.com/photos/a-macbook-air-laptop-in-the-dark-NK-cB-l1cv0?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>'
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # Options: , letter, note, page
categories: Homelab # Options: Writeup, Personal
tags:
    - homelab
    - windows

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

How to use winget for Windows 11.

## What is winget?

It's a package manager for Windows, like choco or apt for debian based linux distros.

If that means nothing to you, then it installs and updates apps. Cool? Cool.

## How to use winget

Let's install [syncthing](https://syncthing.net/) for this example.

`winget search sync` displays a list of matches **sync**.

```asp
Name          Id                      Version  Match          Source
--------------------------------------------------------------------
syncthing     Syncthing.Syncthing     1.27.0                  winget
SyncTrayzor   SyncTrayzor.SyncTrayzor 1.1.29.0 Tag: syncthing winget
syncthingtray Martchus.syncthingtray  1.4.11   Tag: syncthing winget
syncthingctl  Martchus.syncthingctl   1.4.1                   winget
```

Then install a package by 
- the Name `winget install syncthing`,
- or Id `winget install syncthing.syncthing`.

Oh no, that's not the right package.

List out your installed packages with `winget list`.

To uninstall use
- the Name `winget uninstall syncthing`,
- or Id `winget uninstall syncthing.syncthing`.

Double check syncthing is removed from
- `C:\Users\%USERNAME%\AppData\Local\Microsoft\WinGet\Packages` and
- `C:\Users\%USERNAME%\AppData\Local`.

Then install `winget install synctrayzor` for the correct package (optional example).

---

Let me know if you want a syncthing post.

Thanks for reading


