---
title: "Rustscan"
published: 2024-05-25T09:47:04+10:00
# lastUpdated: 2024-05-25T09:47:04+10:00
url: rustscan
alias: # aliases for multiple
    - installing-rustscan
    - 

cover:
    image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Homelab # Homelab, Writeup, Personal
tags:
    - 
    - 

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Make sure you've [Installed Docker](https://mrash.co/docker/).

Here's a bash script to automate the installation:

```bash
#!/bin/bash

# Update, install and enable Docker
sudo apt update -y && sudo apt upgrade -y
sudo apt install -y docker.io
sudo systemctl enable docker --now

# Add current use into docker group
sudo usermod -aG docker $USER

# Pull latest Rustscan
docker pull rustscan/rustscan:latest

# Create a ZSH Aliases File
touch ~/.zsh_aliases

# Add it to ZSH RC
echo """if [ -f ~/.zsh_aliases ]; then
    . ~/.zsh_aliases
fi""" >> ~/.zshrc

# Add the rustscan alias to ZSH Aliases File
echo "alias rustscan='docker run -it --rm --name rustscan rustscan/rustscan:latest'" >> ~/.zsh_aliases

# Source the ZSH RC File
. ~/.zshrc

# Rustscan Examples

echo """ Some Rustscan Examples
rustscan $ip -t 500 -b 1500 -- -A
rustscan -a $ip -g && rustscan $ports -- -sC -sV
"""

```



---

Thanks for reading
