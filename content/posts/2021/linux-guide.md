---
title: Linux Quick Start Guide
author: Mr Ash
type: "post"
published: 2021-08-14
lastUpdated: 2022-11-02
url: "/linux-quick-start-guide/"
image: https://images.unsplash.com/photo-1599227577308-4323e4e2c946?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2Mjg5MTIxMzU&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1704
categories: 
    - Cyber
tags:
    - Linux
    - BASH
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Linux-Quick-Start-Guide-e16j882" width="400px"></iframe> -->

Learning Linux is fun! Beginning Linux is hard.

There’s a lot of free courses and content to help you. But what about a quick start guide to Linux? Getting started with Linux made easy?

No fluff, just a quick and dirty setup to get you started with Linux basics! Well, here it is, the Linux Quick Start Guide. To follow along, install [Ubuntu Linux](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/) and let’s learn how to get started with Linux.

*Disclaimer, this is an ongoing piece of content and is not finished.*

## Introduction

Linux is an open-source operating system with an interesting history and important philosophy.

Linux is built from [UNIX](https://discourse.unixgame.io/t/what-are-the-differences-between-unix-and-linux/71) by [Ken Thompson](https://en.wikipedia.org/wiki/Ken_Thompson), [Dennis Ritchie](https://en.wikipedia.org/wiki/Dennis_Ritchie) from AT&T in 1970. This led to the [GNU project](https://www.gnu.org/) (free Unix-like OS) by [Richard Stallman](https://en.wikipedia.org/wiki/Richard_Stallman) in 1983 under the [GPL](https://en.wikipedia.org/wiki/GNU_General_Public_License), and then the first open-source Linux kernel by [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) in 1991.

The Linux Philosophy is simple, 1) everything is a file, 2) small, single-purpose programs, 3) chain programs together for complex tasks, 4) avoid captive user interfaces and 5) configuration data stored in a text file.

Given its open-source nature, there are countless operating systems built on Linux known as Linux Distributions. [Ubuntu](https://ubuntu.com/) is generally considered the most beginner-friendly distro, see [this guide](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/) for help setting up Linux virtually. This quick start guide refers to Debian-based commands, the UNIX ancestor of Ubuntu.

## Commands

Linux embraces the Command Line Interface (CLI), so should you! Linux’s CLI or shell is called [Bourne Again Shell (BASH)](https://www.techopedia.com/definition/3520/bourne-again-shell-bash), we’ll use a [terminal emulator](https://en.wikipedia.org/wiki/Terminal_emulator) on Ubunutu (or your Linux Debian Distro) to interact with our computer.

The **prompt**, typically shown like `user@device:directory$` is indicating your input from the keyboard. Unlike a Graphical User Interface (GUI), there are no visual elements to interact with.

Instead, **commands** are used to execute programs that are defined by `command [options] [arguments]`. Their default behaviour displays a result but depending on what options and arguments are paired with it. Options (or Switches) alter the behaviour of output, while **arguments** specify command output.

An example of this is ls -la ~/Documents, ls lists files and directories (folders), with the -l option, it displays them as a tabled list and -a displays hidden files or directories. The `~` represents the user home directory and the `/Docuemnts` is the folder path to the `Documents` directory.

Use `hostname` to display the device name and `whoami` to output your username. At anytime you can use the `man` to show a manual for a command, if there is no manual try the command followed by `--help` or `-h`. Try `man ls` or `ls --help`.

`echo` is used to print or write something to the terminal, try `echo 'enter a sentence'`. It’s very useful to chain together with other commands later. Use the `up` and `down` arrows to cycle through previsouly used commands, `!!` to run last command or run `history` to see all used commands. Try `TAB` to auto-complete commands or arguments.

## Navigation

Let’s navigate the Linux filesystem, first use `pwd` to print working or current directory.

Use `cd` to change directories and `ls` to list files in a directory. To specify what directory to navigate to, either use an **absolute** or **relative** path. An **absolute** path starts from the root directory, represented by `/` but a **relative** path starts from the current directory, represented by `.`.

You can use other short hand path navigaters like `..` for the parent directory or `~` for the user home directory. If lost, `cd ~` to go home and start again.

To copy a file or directory use `cp` but to move a file or directory, use `mv`. To make a new directory use the `mkdir` and `rmdir` or `rm -r` will remove them. To display files content, use `cat` which is short for concatenate. If it’s a larger file, use `head` to display the first part or `tail` to display the last.

`touch` will simply create a new file, then `file` will display the file type. To edit a file’s content, use a text editor like vi, vim or nano. Nano is the most beginner-friendly of the three.

Use `find` to find files in directories and `grep` to search through the content of a single file. You can also use `sort` and `unique` to filter through the content of files.

## System

Now you’re moving around, let’s find out some information about your system.

Linux programs rely on other programs which are called dependencies. So programs and their dependencies are called packages. To manage Linux packages we need a package manager, we’ll use `apt`. It’s good practice to run `apt update` and `apt upgrade` with new systems to ensure it has the latest packages.

To install programs, use `apt install <program>` to remove, use `apt remove <program>`. Remember, commands execute programs and they often have the same/similar name.

The Linux filesystem is the folder structure, starting at root `/` there’s `/bin` for system commands, `/boot` with system boot information, `/dev` for device files to access hardware, `/etc` for system and application configuration files. Then `/home` for user sub-directories, `/lib` for shared library files, `/media` mounted devices, `/mnt` for temporary filesystems, `/root` the user root’s home folder. Then `/sbin` which includes executables for sys admin (binary system files), `/tmp` operating system and program temporary file directories can be cleared upon boot or without warning. Lastly, `/usr` contains executable library and manual files, `/var` Variable data e.g. log files, email, web apps, crons &amp; more.

A program running or being executed is known as a process. To see processes on your Linux system, use one of the following command combinations: `ps`, `ps -e`, `ps -ef`, `ps au` or `ps aux`. `PID` is the process identifier, `TTY` is the name of the terminal, `TIME` total time of process and `CMD` command started process.

To turn off your system, use `shutdown now` or to restart, `reboot now`. You can also use these commands to shutdown/reboot at certain times, read the man pages.

## Permissions 

(Coming Soon)

## Networking 

(Coming Soon)

This is Day 17 of [#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to follow the journey!

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

Happy Hacking.