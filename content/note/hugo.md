---
title: "Hugo"
#published: 2023-12-15T13:14:04+10:00
#lastUpdated: 2023-12-15T13:14:04+10:00
url: hugo
alias: # aliases for multiple
    - 
    - 

cover:
    #image: "https://images.unsplash.com/photo-1517134191118-9d595e4c8c2b?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: note # Options: , letter, note, page
categories: language # Options: Writeup, Personal
tags:
    - hugo
    - code

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

[Full Supported Languages List](https://github.com/jincheng9/markdown_supported_languages)

Alias(es)

Here's what I use for my urls:

```
url: hugo
alias: # aliases for multiple
    - post/hugo
    - 
```

But in order for aliases to work, I have to change `aslias` to `asliases`, save. Then change it back to `aslias`. Strange. 

## Markdown All in One

Hands down the best extension to use within VSCode is [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one).

- Paste links over text for automatic linking
- Continues ordered and unordered lists when typing

## Working Checkbox Items

Add the below snippet to footer e.g. `extend_footer.html` in PaperMod.

```javascript
// Clickable checkboxes
const checkboxes = document.querySelectorAll('input[type="checkbox"]');
checkboxes.forEach(checkbox => {
  // remove the disabled attribute; added by kramdown by default
  checkbox.removeAttribute('disabled');
});
```

Thanks to [Gurjot](https://thatgurjot.com/til/clickable-checkboxes-on-jekyll-hugo/)
