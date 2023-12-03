---
title: "{{ replace .Name "-" " " | title }}"
published: {{ .Date }}
lastUpdated: {{ .Date }}
url: "{{ replace .Name "" "-" | title }}"
alias:
    - 
    - 

cover:
    image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: Letter # Options: Letter, Note, Page
categories: Letter # Options: Letter, Note, Page
tags:
    - 
    - 

draft: false

ShowToc: false
# TocOpen: false
---

