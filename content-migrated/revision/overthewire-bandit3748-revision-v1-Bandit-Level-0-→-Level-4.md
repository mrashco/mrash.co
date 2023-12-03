---
id: 4783
title: "Bandit Level 0 \u2192 Level 4"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4783
url: "/?p=4783"
---

Bandit, the beginner Capture The Flag (CTF) game.

Whether you’re familiar with text-based games or have never even thought of playing them (me). This is the perfect CTF for learning Linux.

You’re here to either copy my answers OR learn. Can I ask you to please focus on the learning! It’s okay to peak when you’re so blind it’s crippling you, but please don’t just copy, copy, copy!

Take the time to try, fail and repeat. It’s a massive part of learning. Don’t robe yourself of that.

Okay, lecture over. Let’s CTF!!

Wooow now, one more thing before we go any further. Open something to take notes in, Notion, Text Editor, heck Mircosoft Word. It doesn’t matter. But it’s a great idea to record what you’ve done and how you’ve done it.

Okay. Let’s continue.

## Bandit Level 0

Okay, let’s get started and connect to the game. This is done via Secure Socket SHell (SSH).

This tell’s Linux to run the `ssh` command, connect to `bandit.labs.overthewire.org` via port `2220` and user `bandit0`.

```
<pre class="wp-block-code">```
$ ssh bandit0@bandit.labs.overthewire.org -p2220

```
```

Type `yes` hit `enter` and you’re in! WhooHoo! Nice job.

Take a moment to read the rules and check out the welcome message.

## Bandit Level 0 → Level 1

Okay, now put your game face on, \*grunts\*.

Let’s take a look at our goal:

- The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

I like to copy/paste the goal into my note-taking app and highlight/bold areas that are important. In this case, we’ve got clear instructions to find the readme file.

Okay, let’s look around the machine, find the file and then read it.

We’ll use the `ls` command to view files in the current directory.

Then we’ll `cat` the file we find.

```
<pre class="wp-block-code">```
$ ls

readme

$ cat readme

boJ9jbbUNNfktd78OOpsqOltutMc3MY1

```
```

Great! We got it! I know it’s a random bunch of letters and numbers but in this CTF the “flags” will look like this. Other games might be a bit different, but this unreadable nonsense is a good thing!

Don’t forget to copy that flag by highlighting it and pressing `CTRL + SHIFT + C`.

Let’s confirm this is correct by cutting connection via `bandit0` user and `ssh` into the next level via `bandit1`.

We’ll do that by running the command `exit`.

Now instead of typing or copy/pasting the `ssh` credentials, let’s use the `up` arrow to find our last command.

Let’s just edit the command to make it more usable moving forward. Remove `bandit0@` in the beginning and add `-l bandit1`.

```
<pre class="wp-block-code">```
$ ssh bandit.labs.overthewire.org -p2220 -l bandit1

```
```

Now paste the flag using `CTRL + SHIFT + V` which you can copy from your notes because you’re definitely taking notes, right???

Done! Now it’s time to move on to the next level.

## Bandit Level 1 → Level 2

Alrighty, now it’s getting serious.

First things first, let’s read that goal.

- The password for the next level is stored in a **file** called **–** located in the home directory

Okay, seems easy, same as last round, `ls` then `cat`…right?

Try it, but you’ll see the issue.

We need to specify the exact file path in order for Linux to understand. We’ll add `./` which tells Linux “hey, I’m in this folder”.

```
<pre class="wp-block-code">```
$ ls

-

$ cat ./-

CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

```
```

That looks pretty good!

Let’s follow the same process of `exit` &gt; `up` &gt; change user, in this case, `bandit2` &gt; enter flag as password.

## Bandit Level 2 → Level 3

Training wheels are coming off!

Goal check

- The password for the next level is stored in a **file** called **spaces in this filename** located in the home directory.

Okay, hm, a bit unusal. This shouldn’t be too difficult… shouldn’t be.

If we try and `cat` out to see the file, but type out `spaces in this filename` it treats each word as a separate file. How do we fix this?

After a bit of googling… it’s quite easy. Just add a `\` after each word. But to make it easier, hit `TAB` after typing the first letter and it’ll do it for you!

```
<pre class="wp-block-code">```
$ ls

spaces in this filename

$ cat spaces\ in\ this\ filename

UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

```
```

Flag, got, nice.

Get out of this level and move on to the next one!

## Bandit Level 3 → Level 4

Let’s go beyond `ls` and `cat` and start chaning directory’s (aka folders)!

So what’s the goal?

- The password for the next level is stored in a hidden file in the **inhere** directory.

Okay, our clue is the directory is hidden, tuck that away for now.

Let’s view what’s around and move into our directory using `cd`.

You might notice I’m using `&&` to chain commands together, neet little trick I’ve picked up.

```
<pre class="wp-block-code">```
$ ls

inhere

$ cd inhere && ls

```
```

Okay, so we should see our file… but it’s hidden, so we can’t.

We need to introduce flags, these are like switches we can use to add features to our programs.

`ls` displays files, but if we turn on `-a` it will also display hidden files. Let’s try it!

```
<pre class="wp-block-code">```
$ ls -a

. .. .hidden

$ cat .hidden

pIwrPrtPN36QITSp3EQaw936yaFoFgAB

```
```

Nice! We got em.

Exit and move on to the next level!

## Bandit Level 4 → Level 5

Hello friend, we meet again.

As always, start with the goal.

- The password for the next level is stored in the **only human-readable file** in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

Hmmm, this is new, something known as a human-readable file. Let’s start with the usual poking around and see what we can find.

The only difference is I’ve added the `-l` switch for `ls` to display results in a list with extra detail. Don’t let the extra detail scare you, just enjoy the ordered list for now.

```
<pre class="wp-block-code">```
$ ls

inhere

$ cd inhere && ls -la

drwxr-xr-x 2 root    root    4096 May  7  2020 .
drwxr-xr-x 3 root    root    4096 May  7  2020 ..
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file00
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file01
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file02
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file03
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file04
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file05
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file06
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file07
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file08
-rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file09

```
```

Okay, wow, lots of files… what next??

Let’s take a look at a new command to help us out, `file`.

We’ll use it in junction with a file path and wildcard to display all results of the files. Let’s see what the heck I’m talking about.

```
<pre class="wp-block-code">```
$ file ./*

./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data

```
```

Well well well, what do we have here??

The only ‘human readable’ text I can see is ASCII text… what’s in there? Let’s `cat` it out and see.

```
<pre class="wp-block-code">```
$ cat ./-file07

koReBOKuIDDepwhWk7jZC0RTdopnAYKh

```
```

Would you look at that! We did it!

And that’s it, hope you enjoyed the ride so far.

You’ve got enough skills to keep on going, so exit out and head on to the next level. Enjoy!

- - - - - -

If you have any feedback, please send me a message via [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 4 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [weekly newsletter](https://go.mrash.co/newsletter) to see the learning journey!

Happy Hacking.