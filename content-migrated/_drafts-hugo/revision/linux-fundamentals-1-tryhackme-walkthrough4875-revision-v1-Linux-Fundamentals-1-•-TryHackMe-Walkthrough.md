---
id: 4938
title: "Linux Fundamentals 1 \u2022 TryHackMe Walkthrough"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4938
url: "/?p=4938"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Learning Linux? Great, me too!

Here’s the [Linux Fundamentals 1 Walkthrough](https://tryhackme.com/room/linuxfundamentalspart1) from [TryHackMe](https://tryhackme.com/). Let’s take a look at some of the fundamentals of Linux including common commands, the terminal, your prompt and more. There’s lots to love in Linux, as there’s so many flavours or distributions, the possibilities are endless.

I hope you learn something on your Linux journey! Enjoy TryHcakMe’s Linux Fundamentals 1.

*Disclaimer, for more TryHackMe walkthroughs, see [Linux Fundamentals 2](https://mrash.co/linux-fundamentals-2-tryhackme-walkthrough/) or [Linux Fundamentals 3](https://mrash.co/linux-fundamentals-3-tryhackme-walkthrough/). For more Linux, see [the blog](https://mrash.co/category/cyber/linux/) and the [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/).*

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/HUFTqWKDh7A?feature=oembed" title="TryHackMe Linux Fundamentals 1 Walkthrough" width="800"></iframe></div></figure>## Task 1, 2 &amp; 3

To get started, just read each level and click next once you’ve understood the tasks and content. First up, to answer, what year was the first release of a Linux operating system? Use [Wiki](https://en.wikipedia.org/wiki/Linux) to find the first flag, 199\*, great work!

Before we go any further, let’s connect using [OpenVPN](https://tryhackme.com/access) to TryHackMe’s virtual private network. Download your OpenVPN config file, then use `sudo openvpn /path/to/file/username.ovpn` to start the connection.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOu9qwjw/b0047aba-c8f0-4a02-a988-2353ac9413f2.jpeg?v=c1cb39e80301611f87c9a282c1420ef9](https://p146.p4.n0.cdn.getcloudapp.com/items/nOu9qwjw/b0047aba-c8f0-4a02-a988-2353ac9413f2.jpeg?v=c1cb39e80301611f87c9a282c1420ef9)</figure>Once connected, you can `ssh` into the machine to log in as the user to complete the other levels. Do this using `ssh tryhackme@<ip address>`, don’t forget both username and password are both `tryhackme`.

<figure class="wp-block-image is-resized">![https://p146.p4.n0.cdn.getcloudapp.com/items/P8u6JgEN/87011d57-2da0-471c-8e98-1c66a8649847.jpeg?v=67662adba2f461a2e6575f5c63d8d11c](https://p146.p4.n0.cdn.getcloudapp.com/items/P8u6JgEN/87011d57-2da0-471c-8e98-1c66a8649847.jpeg?v=67662adba2f461a2e6575f5c63d8d11c)</figure><script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>## Task 4 Running Your First few Commands

Alright, now let’s get familiar with the terminal and use your first few commands, `echo` and `whoami`. Start with either one and use the screenshot below to assist you.

It’s recommended to type the commands, again and again, to get your muscle memory engaged. The more you type, the faster you get and the better you’ll be at using the commands you learn.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/jkum9oxW/65d82a2e-a172-4008-b8de-181bdbc6c036.jpeg?v=f27232744ca6edfa73c4ece030e8253b](https://p146.p4.n0.cdn.getcloudapp.com/items/jkum9oxW/65d82a2e-a172-4008-b8de-181bdbc6c036.jpeg?v=f27232744ca6edfa73c4ece030e8253b)</figure>Once you’re comfortable with those commands, tackle the questions in this level/task.

To answer, ‘If we wanted to output the text “TryHackMe”, what would our command be?’ use the following `echo T**H***M*`. And for ‘What is the username of who you’re logged in as on your deployed Linux machine?’ use the `whoami` command.

Nice work!

## Task 5 Interacting With the Filesystem!

Nice, let’s keep going with a few more commands we need to navigate the filesystem. To explain, the filesystem is all the folders and files that are preconfigured and used by you the user and Linux itself.

Start with using the `ls` command to list out the contents of the current directory, and try adding `-l` and `-la` after to see how the one command can be used in different ways. More on these later.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgyxg/30aa34ee-b3cb-48f9-b833-143f3b25f58c.jpeg?v=dbfac633539bdf14f0592c9cdcd0a413](https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgyxg/30aa34ee-b3cb-48f9-b833-143f3b25f58c.jpeg?v=dbfac633539bdf14f0592c9cdcd0a413)</figure>Next, start using `cd` for Change Directories, the term directory can be likened to a folder, its something that stores files inside it. You can use `cd <location>` for example to get to the topmost folder, or root, use cd /. The forward slash is used in file paths to determine the location, but the topmost level only has / as there’s no other directories above it.

If you get lost, use the `~` to get home, that’s the symbol for your logged-in users home directory, so to do that, use `cd ~`. Also, you can manually get there by `cd /home/<username>`.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/P8u6Jg05/73698d4b-b2c4-4beb-961b-36849f1d610c.jpeg?v=80deb3c36dd4d78ca1e045de2dc8d6ef](https://p146.p4.n0.cdn.getcloudapp.com/items/P8u6Jg05/73698d4b-b2c4-4beb-961b-36849f1d610c.jpeg?v=80deb3c36dd4d78ca1e045de2dc8d6ef)</figure>You can also use Print Working Directory to check where you are, so that’s `pwd`. Your prompt in modern Terminal Emulator Shells like BASH can include `pwd` and `whoami` at any given time which is a nice feature to have.

Good work so far, let’s take on the task questions for 5.

- ‘On the Linux machine that you deploy, how many folders are there?’ – use the `ls` command.
- ‘Which directory contains a file?’ – you can `ls folder<1,2,3,4>/` to see the contents.
- ‘What is the contents of this file?’ – use `cat` to concatentate/display the files contents.
- ‘Use the cd command to navigate to this file and find out the new current working directory. What is the path?’ – try use `pwd` for this, but make sure you’ve `cd folder4/` first.

## Task 6 Searching for Files

Good work so far!

Another program/command called `grep` which can search through the contents of a file.

For this level’s question, ‘Use grep on “access.log” to find the flag that has a prefix of “THM”. What is the flag?’ follow the screenshot below.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgyr8/86d3d254-7bc0-46d9-b807-a349031ec721.jpeg?v=4cefe929c62bec7bd36997c0cda7c5f8](https://p146.p4.n0.cdn.getcloudapp.com/items/KouYgyr8/86d3d254-7bc0-46d9-b807-a349031ec721.jpeg?v=4cefe929c62bec7bd36997c0cda7c5f8)</figure>## Task 7 An Introduction to Shell Operators

Almost there, let’s talk Shell Operators, symbols that make our lives easier!

Try it out using the `echo` command like so, `echo hey > welcome` and then `cat welcome`. Cool hey? We can send the outputs of a command to another destination rather than just the terminal’s output on the screen.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uLJlNy/753d2f0b-9ab2-47b3-9911-47ecebc181c2.jpeg?v=9a70955f483346c9a89c4aa25101c0d5](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uLJlNy/753d2f0b-9ab2-47b3-9911-47ecebc181c2.jpeg?v=9a70955f483346c9a89c4aa25101c0d5)</figure>Let’s do the last set of questions for this room.

- “If we wanted to run a command in the background, what operator would we want to use?’ – you’ve got a few options, go over the operators again if you’re unsure.
- ‘If I wanted to replace the contents of a file named “passwords” with the word “password123”, what would my command be?’ – see the screenshot for help below.
- ‘Now if I wanted to add “tryhackme” to this file named “passwords” but also keep “passwords123”, what would my command be’ – same again, see screenthot.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOu9qpvg/b440481c-458c-4aa6-88da-c708a0cb188f.jpeg?v=ed053f1d80ec5e84bdb283d2b3287168](https://p146.p4.n0.cdn.getcloudapp.com/items/nOu9qpvg/b440481c-458c-4aa6-88da-c708a0cb188f.jpeg?v=ed053f1d80ec5e84bdb283d2b3287168)</figure><script async="" src="https://beacon.by/leadcapture/embed/b8fc58269a89cd11"></script>Well done, that’s it! You passed all the levels in the room!

Great work for making it to the end of [TryHackMe’s Linux Fundamentals 1 Room](https://tryhackme.com/room/linuxfundamentalspart1). Stay tuned for lots more Linux content, if you can’t wait, check out [Linux Unhatched Cisco Course Review And Notes](https://mrash.co/linux-unhatched-cisco-course-review-and-notes/) or [Mini Linux Lessons](https://mrash.co/mini-linux-lessons/).

If you have any feedback, let me know, thanks.

This is Day 32 and 35 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, you can follow my [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) too.