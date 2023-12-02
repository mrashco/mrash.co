---
title: Linux Unhatched Cisco Course Review and Notes
author: Mr Ash
type: "post"
published: 2021-07-21
lastUpdated: 2022-11-02
url: "/linux-unhatched-cisco-course-review-and-notes/"
image: https://images.unsplash.com/photo-1580706483913-b6ea7db483a0?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MjY4NjcwNTI&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=2011
categories: 
    - Cyber
tags:
    - Linux
    - BASH
---

Learning Linux?

Well, Linux Unhatched from CISCO Net Academy is a great place to start.

Depending on your experience, this short course could take you a few days or over a week.

It’s free, well structured, easy to read and interactive. Perfect for learning Linux.

Below are my notes for the course, I skipped 14-14.2 as I’ll be coming back to that section.

\*Disclaimer, the course content is owned and shared via CISCO Net Academy.

## Introduction

Learn Linux: fun, free and everywhere.

Linux: Open source kernel OS and used everywhere on everything

Linux CLI: main user-interactive method.

## Basic Command Syntax

CLI (Command Line Interface): powers low-power machines, servers or anything.

Command: program executed via CLI

Typing = process run by OS

- Reads user input (stdin)
- Manipulates data
- Produces output (stduout)

Command rules:

- Names typically describe action.
- They’re case sensitive.
- Default behaviour without options/args.

`command [options...] [arguments...]`

`ls` lists files in directories.

### Arguments

Arguments specify the command output. `ls Documents` lists files in Documents directory.

### Options (switches)

Options alter the behaviour of command output. `ls -l Documents` or `ls Documents -l`

Multiple options (switches) can be used:

`ls -l -r`, `ls -rl` and `ls -lr` are same.

## 3. Printing Working Directory

`pwd [options]` shows current dir

- Use to be used with printers
- `~` = `/home/user/`

## Changing Directories

Files store data e.g. text, graphics &amp; programs.

- Directories are files that provide organizational structure.

`cd [options] [path]`

- `/` root dir and path

Filesystem is a map, paths are the directional steps. Two types:

1. Absoulate: starts from root.
2. Relative: starts from current dir.

`.` current dir

`..` parent dir

`~` home dir

## Listing Files

`ls -l` lists files in actual list.

- File Type
- Permissions
- Hard Link Count
- User Owner
- Group Owner
- File Size
- Timestamp
- Filename

Sorting switches for `ls`

`-t` by timestamp

`-s` by file size

`-r` reverse order

## Administrative Access

`su [options] [username]` temp act as other user via creating new shell aka change users.

- By default, `su` changes to root.
- Use `su -l` to proper login as user.

Prompts change depending on user.

`sudo [options] command` executes commands as other user without creating shell.

- By default, `sudo` uses root.

## Permissions

Determines how users interact with files or dirs. `ls -l [filename]`

- File Type
- Permissions Field
- Owner
- Group
- Other
- Permission Types: r, w, x.
- Read:
    - File: see or copy.
    - Dir: non-details shown.
- Write:
    - File: modified or overwritten
    - Dir: requires execute.
- Execute:
    - File: run as process.
    - Dir: move dirs

## Changing File Permissions

- `chmod` changes file/dir permissions, only by root or owner. `chmod` comes from change mode of access.

Two techniques of `chmod`

1. Symbolic: good changing one set of permissions at a time.
2. Octal: good changing all permissions for users, groups, other.

`chmod [<SET><ACTION><PERMISSIONS> FILE`

- Set: `u`, `g`, `o` or `a`
- Action: `+`, `=` or `-`
- Permissions: `r`, `w` or `x`

`./` indicates commands to run from current dir.

## Changing File Ownership

Owners of files are the creators of files.

`chown` changes ownership of files/dirs, requires root priv.

`chown [OPTIONS] [OWNER] FILE` e.g. `chown root hello.sh`

## Viewing Files

`cat [OPTIONS] [FILE]` concatenate files i.e. good for smaller files.

Pager commands `more` and `less`.

`head [OPTIONS] [FILE]` displays beginning of file, default is 10 lines.

`tail [OPTIONS] [FILE]` displays end of file, default is 10 lines.

`-n` switch allows certain number of lines.

## Copying Files

`cp [OPTIONS] SOURCE DESTINATION`

Must have `x` perm to `cp` file and `w x` perms on destination dir, both `/tmp` and `~` will always have this.

### Copying Files

- `dd [OPTIONS] OPERAND` copies files/partitions at bit level.

### Moving Files

`mv SOURCE DESTINATION` moves files from one to another dir.

`mv <file1> <file2> <file3> destination` moves multiple files at once.

`mv <file1> <newfilename>` easily renames file.

`w x` perms needed on source/dest dirs.

## Removing Files

`rm [OPTIONS] FILE` removes files (almost) permanently.

`rm -r <dir>` removes dirs recurisvley.

`w x` perms needed to `rm` files/dirs.

## Filtering Input

`grep [OPTIONS] PATTERN [FILE]` filters search input from files.

### Regular Expressions

(Skipped)

### Basic Patterns

(Skipped)

## Shutting Down

`shutdown [OPTIONS] TIME [MESSAGE]` requires `date`

## Network Configuration

`ifconfig [OPTIONS]`

`lo` loop back 127.0.0.1

`ping`

## Viewing Processes

`ps [OPTIONS]` `-e` and `-f`

`PID` process identifier.

`TTY` name of terminal.

`TIME` total time of process.

`CMD` command started process.

## Package Management

System to install, update, querie or remove from filesystem.

Debian is the `dpkg` command but `apt-get` is front-end program.

- Update with `apt-get update`
- Search with `apt-cache search`
- Install: `sudo apt-get install [package]`
- Update system: `sudo apt-get update && upgrade`
- Remove: `apt-get remove [package]` and `apt-get purge [package]`

## Updating User Passwords

`passwd [OPTIONS] [USER]` updates user passwords.

- `-S` shows status info.

## Redirection

I/O redirection allows info from CL to be sent to file, device or other commands. Three file descripters:

1. STDIN: Standard Input, information given to a command.
2. STDOUT: Standard Out, information displays from output of command.
3. STDERR: Standard Error, error messages from commands.

`[COMMAND] > [FILE]` STDOUT redirect

`[COMMAND] >> [FILE]` append to file.

User must have `w` perms of files to redirect too.

## Tex Editor

`vi` `vim` or `nano`

- - - - - -

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 14 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.