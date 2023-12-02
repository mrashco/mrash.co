---
title: "Linux Fundamentals 2 - TryHackMe Walkthrough"
author: Mr Ash
type: "post"
published: 2022-02-28
lastUpdated: 2022-11-04
url: "/linux-fundamentals-2-tryhackme-walkthrough/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/X6uRELAK/8de294b5-1c2b-4d23-969d-a1e9cd533ec4.png?v=3f4b4343ecd7e36d601965ac4ac4189b
categories: Cyber
tags:
    - Linux
    - TryHackMe
    - Hacking
---

So you’re learning Linux aye? Welcome aboard!

Here’s the [Linux Fundamentals 2 Walkthrough](https://tryhackme.com/room/linuxfundamentalspart2) from [TryHackMe](https://tryhackme.com/). Let’s take a look at some of the fundamentals of Linux including some more commands, ssh, bash scripting and more.

There’s lots to love in Linux, I hope you learn something here on your Linux journey! Enjoy TryHackMe’s Linux Fundamentals 2.

*Disclaimer, for more, see [Linux Fundamentals 1](https://mrash.co/linux-fundamentals-1-tryhackme-walkthrough/), [Linux Fundamentals 3](https://mrash.co/linux-fundamentals-3-tryhackme-walkthrough/) and [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/). Check out the video guide too:*

## Task 1 and Task 2 Accessing Your Linux Machine Using SSH

To get started, make sure you’re connected to the TryHackMe VPN. If you’d like to automate this, you can create a small bash script.

Create a new file using a text editor, more on this soon, use `nano tryhackme-openvpn` and use the following text and see the screenshot below for help.

```python
#!/bin/bash

sudo openvpn /file/path/<username>/Downloads/<your file>.ovpn
```

![https://p146.p4.n0.cdn.getcloudapp.com/items/bLux4gyv/5cc75f1b-6a2b-47e0-808f-fe21b01eee3a.jpeg?v=69f6e4d0394fae41c40827d5f644d555](https://p146.p4.n0.cdn.getcloudapp.com/items/bLux4gyv/5cc75f1b-6a2b-47e0-808f-fe21b01eee3a.jpeg?v=69f6e4d0394fae41c40827d5f644d555)

Nice, you’ll just have to make the bash script executable using `chmod +x <file name>.ovpn` and hit enter. Running `ls -l` will show you the difference in permissions, see screenshot below.

![https://p146.p4.n0.cdn.getcloudapp.com/items/ApuxZRlW/9ffcef26-a6bf-47f6-b7c5-39069a76fd61.jpeg?v=890bd6bb3af7349d5c137b924fead037](https://p146.p4.n0.cdn.getcloudapp.com/items/ApuxZRlW/9ffcef26-a6bf-47f6-b7c5-39069a76fd61.jpeg?v=890bd6bb3af7349d5c137b924fead037)

Great work, the last step is to `ssh` into the Virtual Machin (VM) and you’re good to go!

Think about it like, OpenVPN has connected you to the TryHackMe network, and then SSH is letting you log in as a user on that network, pretty cool. See the screenshot below for more.

![https://p146.p4.n0.cdn.getcloudapp.com/items/E0uow9m0/e2d5aa4b-dfac-44a5-ba87-38f05835c0ce.jpeg?v=41b44e77e8adf74281961d3bc053e49d](https://p146.p4.n0.cdn.getcloudapp.com/items/E0uow9m0/e2d5aa4b-dfac-44a5-ba87-38f05835c0ce.jpeg?v=41b44e77e8adf74281961d3bc053e49d)

<script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>

## Task 3 Introduction to Flags and Switches

Now it’s time for switches, these are like settings or options you can turn on by using a `-` followed by either a lowercase, uppercase or phrase.

Switches might seem weird at first, but think about how many settings are in your web browser for example. They’re all behind a settings menu, image if you could access any setting with just a single letter, kinda powerful stuff. Sure, you just need to learn the switches, but once you know them, it’s much faster than accessing setting menus every time.

Try using the `ls` command again, but add the switches in the screenshot below.

![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuvGE9k/d789d5bd-f771-462a-983d-486c06803295.jpeg?v=32783c670c0b407f9eb35d68d0c8c102](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuvGE9k/d789d5bd-f771-462a-983d-486c06803295.jpeg?v=32783c670c0b407f9eb35d68d0c8c102)

To learn what switches do what, you can either run the manual page for the command like `man ls` or `ls --help` sometimes commands allow `-h` too.

Let’s go over the task questions:

- ‘What directional arrow key would we use to navigate down the manual page?’ – to explain, the arrow keys act like the scroll wheel on your mouse, you can cycle through your used commands. Up goes up, so down must go…?
- ‘What flag would we use to display the output in a “human-readable” way?’ – so you can mannually search through the help output, but a easier way is to search through it automatically. You can do this use `ls --help | grep "human"` this ‘pipes’ the output from `ls --help` through `grep` allowing you to search the contents against `"human"`, pretty cool hey? See below for an example.

![https://p146.p4.n0.cdn.getcloudapp.com/items/7KuqYpnB/e8db9b53-790a-4a73-9a43-49409c9daee1.jpeg?v=6564c84bed7796ad95904096a7884bad](https://p146.p4.n0.cdn.getcloudapp.com/items/7KuqYpnB/e8db9b53-790a-4a73-9a43-49409c9daee1.jpeg?v=6564c84bed7796ad95904096a7884bad)

## Task 4 Filesystem Interaction Continued

Awesome, more filesystem commands, let’s go! You can go ahead and just make new files using `touch <file name>` and for folders/directories you can use `mkdir <dir name>`.

To delete, use the `rm` command, just be careful to note remove the wrong files or directories, see screenshot below.

![https://p146.p4.n0.cdn.getcloudapp.com/items/yAukw6B2/cac6f6af-6372-4782-b313-c95ddfaa7746.jpeg?v=d2732b42ec10aa5a2d7a66ebacce74b8](https://p146.p4.n0.cdn.getcloudapp.com/items/yAukw6B2/cac6f6af-6372-4782-b313-c95ddfaa7746.jpeg?v=d2732b42ec10aa5a2d7a66ebacce74b8)

To copy, use the `cp` command, see screenshots.

![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuvGE9E/ecffe332-7c00-496c-a6f4-bbaea66215c6.jpeg?v=e68852e53e5c369a675f7449d80d5abe](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuvGE9E/ecffe332-7c00-496c-a6f4-bbaea66215c6.jpeg?v=e68852e53e5c369a675f7449d80d5abe)

To move, use the `mv` command.

![https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgZKA/eaf454d1-584f-49ab-b8fa-0cabaf23ad07.jpeg?v=4954664af55de51d72cf4612368bb6b5](https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgZKA/eaf454d1-584f-49ab-b8fa-0cabaf23ad07.jpeg?v=4954664af55de51d72cf4612368bb6b5)

And if you want to know what type of file a file is, just run the `file` command against it.

![https://p146.p4.n0.cdn.getcloudapp.com/items/5zun0Av2/43d08fe9-d91d-4faf-b864-42845162e98e.jpeg?v=d39788259bb766b1f3a4ae65ac516bf8](https://p146.p4.n0.cdn.getcloudapp.com/items/5zun0Av2/43d08fe9-d91d-4faf-b864-42845162e98e.jpeg?v=d39788259bb766b1f3a4ae65ac516bf8)

![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uLJNB9/cd0600b6-f060-4506-bc08-6041f5d8a22c.jpeg?v=97dc0b435623ea61c74687d50b066688](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uLJNB9/cd0600b6-f060-4506-bc08-6041f5d8a22c.jpeg?v=97dc0b435623ea61c74687d50b066688)

Nice, let’s go over the tasks questions:

- ‘How would you create the file named “newnote”?’ – you can do this is a few ways, but for this task, use the `touch` command.
- ‘On the deployable machine, what is the file type of “unknown1” in “tryhackme’s” home directory?’ – run the `file` command agasint it to find out.
- ‘How would we move the file “myfile” to the directory “myfolder”’ – remember, use the move command like this `mv <old directory> <new directory>`.
- ‘What are the contents of this file?’ – you can use the `cat` command for this one.

## Task 5 Permissions 101 &amp; Task 6 Common Directories

Ah, permissions, it’s very daunting at first, but there’s a method to the madness.

Use the `ls -l` to see the permissions for the current directories files. You’ll see either a `-`, `r`, `w` or an `x` – these stand for read, write and execute. Read means you can see it, write means you can edit it, and execute means you can run it.

To switch users, use the `su` command, but to run an application as another user without switching, use `sudo`. Note, the `sudo` command’s default behaviour runs as root, this is commonly used to allow full authenticated behaviour on a system.

![https://p146.p4.n0.cdn.getcloudapp.com/items/OAu4kgNe/cd8de5c0-88fe-4cd2-82c1-aaa8806e62dd.jpeg?v=61cfee2bb647c20576ef83e251423c8e](https://p146.p4.n0.cdn.getcloudapp.com/items/OAu4kgNe/cd8de5c0-88fe-4cd2-82c1-aaa8806e62dd.jpeg?v=61cfee2bb647c20576ef83e251423c8e)

Okay, time for this tasks questions:

- ‘On the deployable machine, who is the owner of “important”?’ – using `ls -l` see the column showing usernames.
- ‘What would the command be to switch to the user “user2”?’ – `su` is the command, but how do you switch to `user2`?
- ‘Output the contents of “important”, what is the flag?’ – once you switch users, use the `cat` command to display the `important` files output.

Next up is Task 6, let’s go straight to the task questions:

- ‘What is the directory path that would we expect logs to be stored in?’ – the `/var` has variable data like logs.
- ‘What root directory is similar to how RAM on a computer works?’ – RAM is volitale, meaning it’s deleted after a system shut down or reboot, similar to a temporary directory.
- ‘Name the home directory of the root user’ – it’s the same name as the user itself.

![https://p146.p4.n0.cdn.getcloudapp.com/items/RBuyg4kG/617a600f-36d2-4f02-a040-c783b3b072aa.jpeg?v=5189743ce23236c71fa36f9e55f9b22c](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuyg4kG/617a600f-36d2-4f02-a040-c783b3b072aa.jpeg?v=5189743ce23236c71fa36f9e55f9b22c)

<script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>

Nice work, you’ve done Linux Fundamentals 2 from TryHackMe. I hope you enjoyed the room and found this walkthrough helpful, best of luck on your Linux learning journey.

{{<youtube m8X9fGvtgeM>}}

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/m8X9fGvtgeM?feature=oembed" title="TryHackMe Linux Fundamentals 2 Walkthrough" width="800"></iframe></div>

 -->

This is Day 33 and 36 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, you can follow my [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) too.