---
title: "Shells"
# published: 2024-05-25T16:40:59+10:00
# lastUpdated: 2024-05-25T16:40:59+10:00
url: shells
alias: # aliases for multiple
    - 
    - 

cover:
    # image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: note # letter, note, page
categories: shells # Homelab, Writeup, Personal
tags:
    - shells
    - python
    - tty

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

```bash
python -c "import pty; pty.spawn('/bin/bash')"
python3 -c "import pty; pty.spawn('/bin/bash')"

/bin/sh -i

[CTRL+Z]
stty raw -ech;fg
export TERM=xterm
```

---

Thanks for reading
