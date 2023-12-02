---
id: 4784
title: PicoCTF General Skills
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4784
url: "/?p=4784"
---

Welcome, it’s nice to have you here.

My first ever write-up in the Cyber Sec space, I’m excited!

Thanks to [NetworkChuck’s](https://networkchuck.com/) Discord for getting me onto [GynvaelEN’s Hacking Livestream #5](https://www.youtube.com/watch?v=sFdMjvt5W2Y) lead me to find [PicoCTF](https://picoctf.org/).

PicoCTF is a great place to start CTF’s, their beginner friendly options provide a simple step into the space!

Disclaimer, I didn’t realise they were getting more difficult. So I couldn’t complete all the General Skills, 10/12 so far. Honestly, I even cheated and looked at other walkthroughs but still couldn’t replicate the answer to getting the flag.

## Let’s Warm Up

Description: If I told you a word started with **0x70** in **hexadecimal**, what would it start with in **ASCII**?

Hint: Submit your answer in our flag format. For example, if your answer was ‘hello’, you would submit ‘picoCTF{hello}’ as the flag.

50 points

- Answer
    1. Searched `hex to ASCII`
    2. [Found](https://www.binaryhexconverter.com/hex-to-ascii-text-converter), inserted `0x70`, no result.
    3. Searched `what's "x" in hexadecimal?`
    4. [Found](https://forums.anandtech.com/threads/what-is-the-x-in-hexadecimal-strings.923357/) 0x can be ignored.
    5. Converted `70` to ASCII = `p`
    6. 🚩 ***picoCTF{p}***

## Warmed Up

Description: What is 0x3D (base 16) in decimal (base 10)?

Hints: Submit your answer in our flag format. For example, if your answer was ’22’, you would submit ‘picoCTF{22}’ as the flag.

50 points

- Answer
    1. Searched `base 16 to base 10`
    2. Ignored 0x, input `3D`
    3. 🚩 ***picoCTF{61}***

## 2Warm

Description: Can you convert the number 42 (base 10) to binary (base 2)?

Hints: Submit your answer in our competition’s flag format. For example, if your answer was ‘11111’, you would submit ‘picoCTF{11111}’ as the flag.

50 points

- Answer
    1. Searched `base 10 to base 2`
    2. [Found](https://math.tools/calculator/base/10-2), input `42` = `101010`
    3. 🚩 ***picoCTF{101010}***

## what’s a net cat?

Description: Using **netcat** (nc) is going to be pretty important. Can you connect to [jupiter.challenges.picoctf.org](http://jupiter.challenges.picoctf.org) at port 25103 to get the flag?

Hint: nc [tutorial](https://linux.die.net/man/1/nc).

100 points

- Answer
    1. Terminal: `nc [jupiter.challenges.picoctf.org](<http://jupiter.challenges.picoctf.org/>) 25103`
    2. 🚩 ***picoCTF{nEtCat\_Mast3ry\_d0c64587}***

## strings it

Description: Can you find the flag in file without running it?

Hints: [strings](https://linux.die.net/man/1/strings).

100 points

- Answer
    1. Didn’t have `strings` &gt; searched `install strings linux` &gt; [found](https://askubuntu.com/questions/948279/how-to-install-strings-in-ubuntu-server) `apt-get install binutils`
    2. `strings strings | grep -e "picoCTF"` = 🚩 ***picoCTF{5tRIng5\_1T\_d66c7bb7}***

## Bases

Description: What does this **bDNhcm5fdGgzX3IwcDM1** mean? I think it has something to do with bases.

Hint: Submit your answer in our flag format. For example, if your answer was ‘hello’, you would submit ‘picoCTF{hello}’ as the flag.

100 points

- Answers
    1. Searched `bDNhcm5fdGgzX3IwcDM1` &gt; [found](https://www.base64decode.org/) Base64 decoder.
    2. Input `bDNhcm5fdGgzX3IwcDM1`
    3. 🚩 ***l3arn\_th3\_r0p35***

## First Grep

Description: Can you find the flag in **file**? This would be really tedious to look through manually, something tells me there is a better way.

Hints: grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php).

100 points

- Answers
    1. Download file `wget [<https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file>](<https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file>)`
    2. `grep "picoCTF" file`
    3. 🚩 ***grep\_is\_good\_to\_find\_things\_f77e0797***

## Based

Description: To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this **program** to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`

Hint 1: I hear python can convert things.

Hint 2: It might help to have multiple windows open.

200 points

- Answer
    1. Search 1337, search 1337 and search 1337.
    2. Search [base2 to ASCII](https://www.binaryhexconverter.com/binary-to-ascii-text-converter) &gt; input.
    3. Search [base8 to ASCII](http://www.unit-conversion.info/texttools/octal/) &gt; input.
    4. Search [base16 to ASCII](https://onlineasciitools.com/convert-arbitrary-base-to-ascii) &gt; input.
    5. 🚩 ***picoCTF{learning\_about\_converting\_values\_02167de8}***

## plumbing

Description: Sometimes you need to handle process data **outside** of a file. Can you find a way to keep the **output** from this program and search for the flag? Connect to [jupiter.challenges.picoctf.org](http://jupiter.challenges.picoctf.org) 14291.

Hint 1: Remember the flag format is picoCTF{XXXX}

Hint 2: What’s a pipe? No not that kind of pipe… This [kind](http://www.linfo.org/pipes.html).

200 points

- Answer
    1. `nc jupiter.challenges.picoctf.org 14291 | grep -e "picoCTF"`
    2. 🚩 ***picoCTF{digital\_plumb3r\_ea8bfec7}***

## mus1c

Description: I wrote you a song. Put it in the picoCTF{} flag format.

Hint: Do you think you can master rockstar?

300 points

- Answer
    1. Searched `rockstar programming` &gt; [found](https://codewithrockstar.com/) &amp; [wiki](https://esolangs.org/wiki/Rockstar).
    2. Input `lyrics` &gt; output `base10`
    3. [Convert](https://onlineasciitools.com/convert-arbitrary-base-to-ascii) `Base10` to `ASCII`

## flag\_shop

DNC.

## 1\_wanna\_b3\_a\_r0ck5tar

DNC.

- - - - - -

So there’s my first walkthrough, pretty simple so far.

This tested my knowledge of the base numbering systems and ASCII a lot. It’s still not ingrained into my brain, so that means more CTF’s!

I was a bit disappointed I couldn’t complete all twelve, but I’m excited to skill up and tackle them again soon!

If you have any feedback, please send me a message via [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 3 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [weekly newsletter](https://go.mrash.co/newsletter) to see the learning journey!

Happy Hacking.