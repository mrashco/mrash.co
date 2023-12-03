---
id: 4940
title: "Linux Fundamentals 3 \u2022 TryHackMe Walkthrough"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4940
url: "/?p=4940"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Welcome to [Linux Fundamentals 3](https://tryhackme.com/room/linuxfundamentalspart3) [TryHackMe Walkthrough](https://tryhackme.com/), the finale of the Linux Fundamental rooms on TryHackMe.

Let’s learn some Linux skills and common utilities around automation, package management, and service/application logging. Are you keen? Yeah!

Let’s go on with Linux Fundamentals 3 TryHackMe Walkthrough.

*Disclaimer, see [Linux Fundamentals Part 1](https://mrash.co/linux-fundamentals-1-tryhackme-walkthrough/) and [Linux Fundamentals Part 2](https://mrash.co/linux-fundamentals-2-tryhackme-walkthrough/) for more.* Also, see the video walkthrough too:

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/H__C8leoU_4?feature=oembed" title="TryHackMe Linux Fundamentals 3 Walkthrough" width="800"></iframe></div></figure>## Task 1 Introduction &amp; Task 2 Deploy Your Linux Machine

Alright, you should be a pro with connecting to TryHackMe’s VPN via OpenVPN and ssh-ing into the TryHackMe user via the provided ip address.

If not, check your learning bro, go back to the earlier rooms, jks, just use the screenshot below to help you.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuzBqk7/a922b680-afb1-4230-a2e6-df17f61b1f41.jpeg?v=81ce31d9af194285598573172f37d9c1](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuzBqk7/a922b680-afb1-4230-a2e6-df17f61b1f41.jpeg?v=81ce31d9af194285598573172f37d9c1)</figure>Once you’re connected, let the room begin!

<script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>## Task 3 Terminal Text Editors

You’re probably familiar with text editors like notepad, Microsoft’s Word, Google Doc or Notion, Linux has its own text editors to choose from.

Start with `nano` and later, not in this room, but later, use `vim`.

Try creating a new file in the current directory using `nano myfile`.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/mXuJ0YNe/d6ad664f-8af1-4793-bd54-0c22a537bb24.jpeg?v=71e6a08fc063c7001729799e6f6bbcba](https://p146.p4.n0.cdn.getcloudapp.com/items/mXuJ0YNe/d6ad664f-8af1-4793-bd54-0c22a537bb24.jpeg?v=71e6a08fc063c7001729799e6f6bbcba)</figure>Now, let’s tackle the task question:

- ‘Edit “task3” located in “tryhackme”‘s home directory using Nano. What is the flag?’ – you could just cat out the file, but in this case, use `nano <file name>` to practice it.

## Task 4 General/Useful Utilities

If we’re using a terminal, there’s no nice web browser to navigate to a website and download our fav HD wallpaper pack, so how do we download? Enter the `wget` command, start with checking out the `man` pages for it.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/llu6PEbR/c1f4b9b4-367d-43bc-ace4-33f47f73da34.jpeg?v=10f1b94b7671e670bdbc2da19589c60e](https://p146.p4.n0.cdn.getcloudapp.com/items/llu6PEbR/c1f4b9b4-367d-43bc-ace4-33f47f73da34.jpeg?v=10f1b94b7671e670bdbc2da19589c60e)</figure>Okay, let’s spin up the python3 web server using `python3 -m http.server` to download a file using `wget`. Note, the system we’re logged in to already has the file, but it’s only accessible for the root user, so this is a nice way to download it to get access, keep this in mind for future rooms.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/9ZuD5mO2/52f2fd19-b09d-4768-80c2-79301d9f5498.jpeg?v=fe229bf215f029d4360fe908224bd620](https://p146.p4.n0.cdn.getcloudapp.com/items/9ZuD5mO2/52f2fd19-b09d-4768-80c2-79301d9f5498.jpeg?v=fe229bf215f029d4360fe908224bd620)</figure>Great, now let’s download the hidden file via web server using `wget http://<ip address>:8000/.flag.txt` see the screenshot below for help.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/o0uZWRlD/9c1edf22-3117-4004-9bb1-b10b03a8b773.jpeg?v=c0170ba90286328de589da4a8efc5b45](https://p146.p4.n0.cdn.getcloudapp.com/items/o0uZWRlD/9c1edf22-3117-4004-9bb1-b10b03a8b773.jpeg?v=c0170ba90286328de589da4a8efc5b45)</figure>Then it’s a case of using `cat`… and after many attempts (for me), see the contents of the downloaded flag file, see screenshot below. This will help you with the ‘What are the contents?’ question.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Bludnoe4/29e09bfe-be93-4a66-a1b1-af42e3271727.jpeg?v=94cf30f5ace2b0eefa8f44c174958016](https://p146.p4.n0.cdn.getcloudapp.com/items/Bludnoe4/29e09bfe-be93-4a66-a1b1-af42e3271727.jpeg?v=94cf30f5ace2b0eefa8f44c174958016)</figure>## Task 5 Processes 101

Next up we’ve got processes. To explain, a program that is in the state of running is known as a process, it’s in the ‘process’ of running. Use the `ps` to see current processes on your system from your logged-in user.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/6quEjZpN/678fbf7d-3444-4ea4-a6e5-f6639578a972.jpeg?v=a64f3bf7f89a189e21366498ce065789](https://p146.p4.n0.cdn.getcloudapp.com/items/6quEjZpN/678fbf7d-3444-4ea4-a6e5-f6639578a972.jpeg?v=a64f3bf7f89a189e21366498ce065789)</figure>Then use `ps aux` to see processes from other users.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/JruGKOYY/5ad131ee-f9ef-4b83-83ce-f8a0946dde98.jpeg?v=13069ec27bdba42418bb6a4f11323fee](https://p146.p4.n0.cdn.getcloudapp.com/items/JruGKOYY/5ad131ee-f9ef-4b83-83ce-f8a0946dde98.jpeg?v=13069ec27bdba42418bb6a4f11323fee)</figure>Now try using `top` to see the live state of processes, this is much more like running Task Manager in a Windows Desktop environment.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/6quEjZpq/e2551f90-506e-40b4-84bb-b34e24e6882e.jpeg?v=9b94f878d85e82b7f2efcafaab831f9c](https://p146.p4.n0.cdn.getcloudapp.com/items/6quEjZpq/e2551f90-506e-40b4-84bb-b34e24e6882e.jpeg?v=9b94f878d85e82b7f2efcafaab831f9c)</figure>So cool, you can see processes running on your system, but how do you stop one?

Let’s do a little test, run `nc -lp 1337`, this start’s a listening command called `netcat` and then find the PID via `ps` and then using the `kill` command to stop it.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/NQuxyNm2/959f3979-29a3-4291-8723-a7cdf2438810.jpeg?v=3f279829cc047ea94010a8d015208bf4](https://p146.p4.n0.cdn.getcloudapp.com/items/NQuxyNm2/959f3979-29a3-4291-8723-a7cdf2438810.jpeg?v=3f279829cc047ea94010a8d015208bf4)</figure>Cool right? The PID is a unique numeric value for each process, if you find the PID, you can kill the process.

Next, let’s run the `echo` command and output it in the background using the `&` operator. Once you do that, then run the `fg` command which brings anything you’ve put in the background, to the foreground. If you put multiple commands to the background, you can us `fg <1,2,3 etc>` to get the command back, it goes in order of when it was put in the background.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Z4u1W74P/9a5f4026-e141-47ab-9274-c801c1aa487b.jpeg?v=1a30cedd82842ef6ea1374baed795471](https://p146.p4.n0.cdn.getcloudapp.com/items/Z4u1W74P/9a5f4026-e141-47ab-9274-c801c1aa487b.jpeg?v=1a30cedd82842ef6ea1374baed795471)</figure>Nice work, let’s see the task questions:

- ‘If we were to launch a process where the previous ID was “300”, what would the ID of this new process be?’ – in the example given, a processes PID with 60, the next process would be 61.
- ‘If we wanted to cleanly kill a process, what signal would we send it?’ – it’s not kill, it’s something that would “do some cleanup tasks beforehand”.
- ‘Locate the process that is running on the deployed instance (YOUR\_MACHINE\_IP). What flag is given?’ – see the screenshot below for more help one this one, you can `grep` out the results to help searching.
- ‘What command would we use to stop the service “myservice”?’ – using the `systemctl` command against `myservice` … you could use, `stop`?
- ‘What command would we use to start the same service on the boot-up of the system?’ – you could use the same as the previous question, but `enable`?
- ‘What command would we use to bring a previously backgrounded process back to the foreground?’ – `fg` for sure.

Passing, or piping the output from `ps aux` into `grep` to find the flag.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/eDulN5D9/06b23514-ccc4-4216-b611-74900497425c.jpeg?v=c15724c9cb73ebb73678978feff058b1](https://p146.p4.n0.cdn.getcloudapp.com/items/eDulN5D9/06b23514-ccc4-4216-b611-74900497425c.jpeg?v=c15724c9cb73ebb73678978feff058b1)</figure>## Task 6 Maintaining Your System: Automation

Ah, crontabs, automating our system, crons are such a powerful tool, let’s have a look at it all in a bit of detail. You can explore crontabs using the `crontab -e` command and switch to open the crontab file to see automated tasks.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/X6u8ZE60/8724e3f3-3502-4c48-b243-60ce3fdb8959.jpeg?v=fde115f6573097f15c9bb2831ad616b7](https://p146.p4.n0.cdn.getcloudapp.com/items/X6u8ZE60/8724e3f3-3502-4c48-b243-60ce3fdb8959.jpeg?v=fde115f6573097f15c9bb2831ad616b7)</figure>Okay, the task questions:

- ‘When will the crontab on the deployed instance (MACHINE\_IP) run?’ – using `crontab -e` and the arrows keys to navigate the file, there’s one entery in the crontab config file, but what time will it be deployed? @\*\*\*\*\*\*…

Note, Task 7 is just a read task, not questions or flags to discuss, but make sure you go over it!

## Task 8 Maintaining Your System: Logs &amp; Outro

Okay, system logs, also known as variable data. Remember from last Linux Fundamentals room, this type of data is held in the `/var/log` directory. Use the `cd` command to navigate there and `ls -la` to see what’s in the location.

To access the `access.log.1` file and find ip of a user and the file that was accessed, you can use the `cat` command. This will help you with the questions ‘What is the IP address of the user who visited the site?’ and ‘What file did they access?’

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/WnuqQynn/3b771ddf-3ebd-4628-9800-d4785c5b340b.jpeg?v=43db9b678005f536610518d4f46de8c4](https://p146.p4.n0.cdn.getcloudapp.com/items/WnuqQynn/3b771ddf-3ebd-4628-9800-d4785c5b340b.jpeg?v=43db9b678005f536610518d4f46de8c4)</figure><script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>Well done, that’s it for the Linux Fundamentals 3 Room from TryHackMe, you did it!

I hope you’ve learnt a lot and are feeling comfortable with the terminal and command-line interface. Don’t forget to keep practising, your Linux journey is only just beginning!

This is Day 34 and 37 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, you can follow my [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) too.