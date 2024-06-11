---
title: "Git"
published: 2023-12-15T11:51:09+10:00
lastUpdated: 2023-12-15T11:51:09+10:00
url: git
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # Options: post, letter, note, page
categories: Code # Options: Writeup, Personal
tags:
    - git
    - code

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Just a few notes/things to remember while using git.

Typical git process:
- `git pull $link`
- `git add .`
- `git commit -m 'v0.1'`
- `git push $link`

Switch branches from master to main
- `git branch -m master main`

If errors:
`git pull --rebase`
