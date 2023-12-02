---
id: 3934
title: Mini Linux Lessons
author: Mr Ash
type: "post"
guid: https://mrash.co/?p=3934
url: "/mini-linux-lessons/"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
ekit_post_views_count:
- '684'
- '684'
image: /wp-content/uploads/2021/05/pexels-photo-4144923.jpeg
categories: "['Linux']"
---

Welcome to my Mini Linux Lessons post! (updated randomly)

While learning Linux you’ll learn a lot! So I’m making an unordered list of mini Linux lessons I’ve learnt while following videos, courses or other content.

If it’s small enough, i.e. it can be summed up in a short paragraph or two, then it won’t get its own blog post, rather it’ll be thrown in here.

Without further ado, here are’s a random collection of Linux lessons!

## Using ifconfig

A basic networking toolset in Linux is called [Net Tools](https://wiki.linuxfoundation.org/networking/net-tools) which has one of the most used commands, `ifconfig`.

Let’s learn how to use it, but first, we’ll install it and run the command:

```
<pre class="wp-block-code">```
sudo apt install net-tools

ifconfig
```
```

Now let’s stop, check and start up your network adapter

```
<pre class="wp-block-code">```
sudo ifconfig eth0 down

ifconfig # notice it's missing

sudo ifconfig eth0 up

ifconfig # notice it's back up!
```
```

How easy is that? You’re now able to easily make changes to your network adapter card if needed.

You’ll find other networking tools that are installed alongside `ifconfig` like `arp` which may be useful in the future, it’s worth noting they exist.

## Checking md5 and sha1 hashes

To test, download [Mr Robot](https://www.vulnhub.com/entry/mr-robot-1,151/) from VulnHubs… I should’ve picked a smaller file.

Check the hash for each md5 and sha1:

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/wbu61xg4/94df74bb-c2ce-4705-85de-71fe95ebd7d9.jpeg?v=3e1e5ca4fb94a7932416755bd13515f7](https://p146.p4.n0.cdn.getcloudapp.com/items/wbu61xg4/94df74bb-c2ce-4705-85de-71fe95ebd7d9.jpeg?v=3e1e5ca4fb94a7932416755bd13515f7)</figure></div>Now let’s verify the integrity of your downloaded file.

We’ll be using Kali Linux via WSL but any distro should do the trick.

First, `cd` to the downloaded area:

```
<pre class="wp-block-code">```
cd /mnt/c/Users/Ashley/Downloads/ && ls

```
```

```
<pre class="wp-block-code">```
md5sum mrRobot.ova
bc02c42815eac4e872d753e1fd12ddc8  mrRobot.ova

sha1sum mrRobot.ova
dc0eb84da4c62284c688590ee092868ce84a09ab  mrRobot.ova

```
```

This [post](https://technastic.com/check-md5-checksum-hash/) is a much better look into this entire process.

## Install Deskop GUI on Ubuntu Server

I find I’m using Ubuntu Server more and more, but I’m still not 100% comfortable in the CLI world all the time.

Let’s install the classic Ubuntu Desktop Graphical User Interface (GUI) on your Ubuntu Server.

It’s a simple process, just use the following commands:

```
<pre class="wp-block-code">```
sudo apt install tasksel

sudo  tasksel install ubuntu-desktop

reboot now
```
```

- - - - - -

Thanks for reading my random learning journey of Linux, I hope you’re having fun on yours!

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 12 and 15 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.