---
title: "Docker"
published: 2023-12-20T15:28:06+10:00
lastUpdated: 2023-12-20T15:28:06+10:00
url: docker
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://images.unsplash.com/photo-1568430462989-44163eb1752f?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    # alt: "<alt text>"
    caption: 'Photo by <a href="https://unsplash.com/@toddcravens?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Todd Cravens</a> on <a href="https://unsplash.com/photos/blue-whale-on-sea-lwACYK8ScmA?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>'
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Homelab # Homelab, Writeup, Personal
tags:
    - docker 
    - homelab

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Let's learn Docker and set it up.

## What's Docker?

Complicated haha!

It's a way to install, maintain and run applications.

But apps are self-contained, hence containers.

Docker allows networking and lots more.

## How to setup Docker

Best way is to follow [the docs](https://docs.docker.com/engine/install/).

## Troubleshooting Docker

You might see an error such as
- `WARNING: Error loading config file: /root/.docker/config.json: read /root/.docker/config.json: is a directory`

For that, do the following [from here](https://github.com/docker/for-win/issues/808):

```bash
sudo rm -fr /root/.docker/config.json

sudo echo '{"credsStore":"wincred"}' >> /root/.docker/config.json

```

---

Thanks for reading
