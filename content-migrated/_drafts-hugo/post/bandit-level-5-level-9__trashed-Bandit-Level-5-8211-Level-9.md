---
id: 3896
title: Bandit Level 5 &#8211; Level 9
author: Mr Ash
type: "post"
guid: https://mrash.co/?p=3896
url: "/?p=3896"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
ekit_post_views_count:
- '750'
fifu_image_url:
- https://p146.p4.n0.cdn.getcloudapp.com/items/o0uXZXnv/9588388a-5d0b-4842-8834-33486290deb4.jpg?v=e56463c3ab15deb00b445da01340de0e
image: https://p146.p4.n0.cdn.getcloudapp.com/items/o0uXZXnv/9588388a-5d0b-4842-8834-33486290deb4.jpg?v=e56463c3ab15deb00b445da01340de0e
categories: "['Linux']"
---

Welcome to another instalment of the Bandit CTF series!

This is the best way to learn Linux, BASH, terminals, commands and everything in between!

Go to [Bandit Level 0 → Level 4](https://mrash.co/bandit-level-0-level-4/) if you need help with earlier levels.

Let’s `ssh` in to Bandit:

```
<pre class="wp-block-code">```
$ ssh bandit.labs.overthewire.org -p 2220 -l bandit5

```
```

You’ll need the password from the previous level.

## Bandit Level 5 → Level 6

Let’s get started by `ls -la` and see what we have.

```
<pre class="wp-block-code">```
total 24
drwxr-xr-x  3 root root    4096 May  7  2020 .
drwxr-xr-x 41 root root    4096 May  7  2020 ..
-rw-r--r--  1 root root     220 May 15  2017 .bash_logout
-rw-r--r--  1 root root    3526 May 15  2017 .bashrc
drwxr-x--- 22 root bandit5 4096 May  7  2020 **inhere**
-rw-r--r--  1 root root     675 May 15  2017 .profile

```
```

Ah, let’s go into the `inhere` directory via `cd inhere && ls -la`.

Using the `&&` lets us stack together a series of commands, this way we 1) change directories and 2) list out the files in the new directory all at once, so cool!

```
<pre class="wp-block-code">```
total 88
drwxr-x--- 22 root bandit5 4096 May  7  2020 .
drwxr-xr-x  3 root root    4096 May  7  2020 ..
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere00
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere01
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere02
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere03
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere04
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere05
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere06
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere07
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere08
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere09
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere10
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere11
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere12
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere13
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere14
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere15
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere16
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere17
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere18
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere19

```
```

…wow! We’ve got a lot of directories to search through now…

Hmm, there must be a better option to automatically search these folders! Enter the `find` command, with it we can search multiple directories and pass it certain switches to narrow down our results, let’s test it out.

```
<pre class="wp-block-code">```
$ find .

```
```

This runs `find` in the current directory, that’s what the `.` is for.

We can be more specific and use switches like `-type` or `-size` to find exactly what we’re looking for.

Let’s go back and get a clue from [Bandit Level 5 → Level 6](https://overthewire.org/wargames/bandit/bandit6.html):

*The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:*

*human-readable 1033 bytes in size not executable*

Okay, so we’ve got some hints for what file we’re trying to find. Let’s use the `-size` switch with the byte size and see what we get.

```
<pre class="wp-block-code">```
$ find . -size 1033

```
```

That’s weird, no luck! That’s because we need to specify what file size exactly, 1033 is just a number. Let’s search it up!

Thanks to [linuxconfig.org](https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size) we know we need to use `c` for bytes.

\*Don’t forget to use the up arrow to see last command!

```
<pre class="wp-block-code">```
$ find . -size 1033c
./maybehere07/.file2

```
```

Cool, look at that! Now we have only one search result, let’s see if we can `cat` it out and view it.

```
<pre class="wp-block-code">```
$ cat ./maybehere07/.file2
banditflag5-6{*****}

```
```

We got it! Now `exit` out and let’s go again!

\*Since my first few writeups I’ve learnt sharing flag’s isn’t the best idea as it allows anyone to simply copy/paste their way through without trying or trying.

## Bandit Level 6 → Level 7

Let’s jump into the next one head first and see what we get!

```
<pre class="wp-block-code">```
$ ls -la

```
```

Okay, strange, nothing there. Maybe I should read the goal first after all!

*The password for the next level is stored somewhere on the server and has all of the following properties:*

*owned by user bandit7 owned by group bandit6 33 bytes in size*

Ah, so the file isn’t within the `bandit6` directory, it’s somewhere else. No worries, let’s look up how to use the `find` command to get the right switches.

```
<pre class="wp-block-code">```
$ find --help

```
```

After looking a bit at the wall text, I see `-user NAME` and `-group NAME`, I think they’re what we’re after. We’ll use it with `-size` from the last level too.

```
<pre class="wp-block-code">```
$ find -user bandit7 -group bandit6 -size 33c

```
```

No luck! What did we forget?

The location! Currently, we haven’t specified where to look, remember it’s hidden anywhere on the server.

```
<pre class="wp-block-code">```
$ find / -user bandit7 -group bandit6 -size 33c

```
```

Good, it’s working! Bad there’s so many files we don’t have access to, how do we only see accessible files? One way is to remove the errors, as ‘Permission denied’ is an error, we can redirect those results elsewhere.

Thanks to [cyberciti.biz](https://www.cyberciti.biz/faq/unix-linux-redirect-error-output-to-null-command/) for explaining `stdin`, `stdout` and `stderr`, it’s worth reading over that aritcle to understand more.

```
<pre class="wp-block-code">```
$ find / -user bandit7 -group bandit6 -size 33c **2>/dev/null**
/var/lib/dpkg/info/bandit7.password

```
```

How cool? We got one search result, that makes life a lot easier.

The `2>/dev/null` may seem very strange at first. The `2` stands for `stderr` which is the errors we have as a result of our search. The `>` redirects and the `/dev/null` is a nothing space directory we can dump everything.

So, `cat` that sucker and grab your flag!

```
<pre class="wp-block-code">```
$ cat /var/lib/dpkg/info/bandit7.password
banditflag6-7{*****}

```
```

## Bandit Level 7 → Level 8

Let’s not read the instructions just yet! `ls` away my friends!

Ah, a simple `data.txt` file, this seems too easy to be real.

Let’s `cat` and …oh gosh… so much data, so much!

Hm, maybe we’ll go back to the hints now:

*The password for the next level is stored in the file **data.txt** next to the word **millionth.***

Okay, so we need to somehow search within the file and output the flag. Our only hint we have is it’s next to the word millionth.

`grep` is the command for the job, it searches for patterns in a file.

Let’s run `grep --help` to get familiar with it, we’re looking for a switch that’s simple enough to match our word with it. Let’s try `-e` or `-regexp=PATTERN`, that should do it!

```
<pre class="wp-block-code">```
$ grep data.txt -e millionth
banditflag7-8{*****}

```
```

Would you look at what we have here… a flag!

Let’s `exit` out and head over the next level!

## Bandit Level 8 → Level 9

Same as always, `ls` and see what we’re working with.

Looks like another `data.txt` file with even more ‘hard to read’ text.

Back to the [instructions](https://overthewire.org/wargames/bandit/bandit9.html):

*The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.*

We could use `grep` and put together a long `regex` to output what we need, but I’m not a wizard.. so we’ll be using `sort` and `uniq`.

First, let’s understand `sort` it’s similar to `cat` but run it against the `data.txt` and see the difference.

```
<pre class="wp-block-code">```
$ sort data.txt

```
```

Everything is sorted, cool.

But how do we then find the unique flag? `uniq` of course.

Try it:

```
<pre class="wp-block-code">```
$ uniq data.txt

```
```

Hm, that didn’t work… that’s because we need to use them together. Since they’re separate commands, we’ll use the `|` pipe to chain it together.

```
<pre class="wp-block-code">```
$ sort data.txt | uniq

```
```

Still no luck, let’s run `uniq --help` and see if there’s a switch that can help.

Yep! `-u` which only prints unique lines, that sounds perfect!

```
<pre class="wp-block-code">```
$ sort data.txt | uniq - u
banditflag8-9{*****}

```
```

Done! We got there thanks to [stackoverflow](https://stackoverflow.com/questions/12782827/how-to-find-the-particular-text-stored-in-the-file-data-txt-and-it-occurs-only).

## Bandit Level 9 → Level 10

Our final level together, for now, let’s `ls` this thing.

Another `data.txt` file, let’s `cat` it.

Ah heck, it was a trap! Use `clear` and we’ll go back to the [instructions](https://overthewire.org/wargames/bandit/bandit10.html):

*The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.*

Okay, so we need to search through the file and somehow use `=`… let’s give it a shot! Maybe we’ll try `grep` again from the earlier level.

```
<pre class="wp-block-code">```
$ grep data.txt -e =
Binary file data.txt matches

```
```

[StackExchange](https://unix.stackexchange.com/questions/335716/grep-returns-binary-file-standard-input-matches-when-trying-to-find-a-string) shows us that since the `data.txt` file starts with non-text, it treats it as binary and therefore won’t search it. Dam.

Let’s look at the other commands we can use.

There’s one called `strings`, let’s take a closer look with `strings --help`

If we use this commands and `|` pipe `grep` with a few `=` … we should be good to go, let’s try it!

```
<pre class="wp-block-code">```
$ strings data.txt | grep ===
========== the*2i"4
========== password
Z)========== is
&========== banditflag9-10{*****}

```
```

It’s not the prettiest method, it’s probably not the best way either, but it worked!

- - - - - -

Thanks for reading along with my bandit CTF journey! It’s been nice to have you.

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 9 and 57 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [weekly newsletter](https://go.mrash.co/newsletter) to see the learning journey!

Happy Hacking.