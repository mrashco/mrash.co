---
title: {{ replace .Name "-" " " | title }}
published: {{ .Date }}
# lastUpdated: {{ .Date }}
url: {{ .Name }}
description: "" # Prompt: Write an SEO description for the blog post {{ replace .Name "-" " " | title }}. Keep it 320 characters or less, use the title exactly as is once.
alias: # Use aliases for multiple
    - 
    - 

cover:
    # image: "IMAGE_URL"
    # alt: "ALT_TEXT"
    # caption: "CAPTION_TEXT"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: TYPE_HERE # post, letter, note, page
categories: CATEGORY_HERE # Homelab, Writeup, Personal
tags: # Prompt: Write 10 tags for {{ replace .Name "-" " " | title }} in YAML format, use code block 
    - 
    - 

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

<!--CONTENT_HERE-->