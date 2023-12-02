---
title: Crack The Hash TryHackMe Walkthrough
type: post
url: "/crack-the-hash-tryhackme-walkthrough/"
image: "https://p146.p4.n0.cdn.getcloudapp.com/items/BluWG9Xn/b7248fbd-b8f4-44b6-b6d0-bc6994216cae.jpg?source=viewer&v=e864944d13a2594d2db87a391fb10436"
date: 2022-10-17
categories: Cyber
tags:
    - TryHackMe
    - Capture The Flag
    - Hacking
---

Let’s tackle [Crack The Hash](https://tryhackme.com/room/crackthehash), another TryHackMe room full of hash-cracking challenges.

If you’d like a video walkthrough, then see the linked video below for a full guide to [Crack The Hash](https://tryhackme.com/room/crackthehash).

{{< youtube euiuIzHaiLk>}}

Quickly, what is a hash and hashing in general?

“Hashing serves the purpose of ensuring integrity, i.e. making it so that if something is changed you can know that it’s changed. Technically, hashing takes arbitrary input and produce a fixed-length string…” — Daniel Miessler, [Hashing vs. Encryption vs. Encoding vs. Obfuscation](https://danielmiessler.com/study/encoding-encryption-hashing-obfuscation/)

Okay, let’s get into this TryHackMe [Crack The Hash](https://tryhackme.com/room/crackthehash) room. There’s no more than a question, *can you complete the level 1 tasks by cracking the hashes?*

## Task 1.1

Fire up your Linux distro of choice and your preferred cracking tool. For me, I’ll start with John The Ripper, or `john` for short. To get started, have a quick refresher or catchup on `john` via [tazusec](https://tzusec.com/crack-password-hashes-from-linux-with-john-the-ripper/).

Feel free to copy each has from the room into a `hash.txt` either by `echo '<hash>' > hash.txt`, or by `nano hash.txt` and pasting it in.

The hash in question is as follows `48bb6e862e54f2a795ffc4e541caed4d`, what a beaut!

So generally you can run `john <format> <wordlist> <hash>`, if you don’t know the format, `john` will try and guess for you. In this case, you can use the `--format=RAW-MD5` format flag with the classic `rockyou.txt` file.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/X6uQRwv1/4cdf97cf-161c-4d1e-be9b-02eaeb79d179.jpg?source=viewer&v=cd6d994efee8826224033593df9f790d)

To determine hashes you can run your hash tool against it or use a hash tool like [Hash Type Identifier](https://hashes.com/en/tools/hash_identifier). I think over time we’ll learn the differences between commonly used hashing and more effectively identify them ourselves. In due time my friend.

In this case, it’s an MD5 (message-digest algorithm), “a cryptographically broken but still widely used hash function producing a 128-bit hash value… it has been found to suffer from extensive vulnerabilities.” — Wikipedia, [MD5](https://en.wikipedia.org/wiki/MD5)

So yeah, don’t use MD5 in production or anywhere but to verify data integrity. I know [WordPress used MD5 for a while](https://stackoverflow.com/questions/1045988/what-type-of-hash-does-wordpress-use), so it’s been around for a while.

## Task 1.2

Great, so for the next hash `CBFDAC6008F9CAB4083784CBD1874F76618D2A97`, mmhm, this one has a particularly nice ring to it. Run `john <wordlist> hash.txt` this time to let `john` do the heavy lifting.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/Qwudnpy9/320444ef-3ee8-4342-b5d8-0ab818518f24.jpg?source=viewer&v=fb1bc48e2f965eea4d38b484862d2dbd)

It’s identified as the SHA-1 (Secure Hash Algorithm 1) hash type, “a cryptographically broken but still widely used hash function which takes an input and produces a 160-bit (20-byte) hash value” — Wikipedia, [SHA-1](https://en.wikipedia.org/wiki/SHA-1).

## Task 1.3

Moving on, let’s crack `1C8BFE8F801D79745C4631D09FFF36C82AA37FC4CCE4FC946683D7B336B63032`, we’ve got a big one boys.

Okay, `echo` that sucker into your `hash.txt` and let’s get started. Running `john <wordlist> hash.txt` this time will give you a lot of suggestions, sometimes it’s a guessing game.

But after trial and error, the flag `--format=RAW-SHA256` is a winner-winner chicken dinner.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/8Lu10LEo/9c0190fa-63f5-4193-a480-cba5a88920e5.jpg?source=viewer&v=c2f1764b20511e3f6ace7f97cb21d472)

So SHA256 is a part of the “SHA-2 family”, it’s “computed with eight 32-bit… words” and “used for authenticating Debian software packages” — Wikipedia, [SHA-2](https://en.wikipedia.org/wiki/SHA-2). Good to know, we use SHA256 all the time on Linux, very cool.

## Task 1.4

Next up you’ve got `$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom` as the hash, interesting. Due to the inclusion of special characters such as `$`, it’s easier to `nano hash.txt` and paste in the hash this time.

For more help, use [Pentest Monkey’s John Hash Formats](https://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats) and [Hashcat’s example\_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes).

There’s an extra step involved with this one, the hint says “this type of hash can take a very long time to crack, so either filter rockyou for four character words, or use a mask for four lowercase alphabetical characters.”

Let’s take the advice and `cat <wordlist> | grep -o -w '\\w\\{4\\}' <new-wordlist>`, thanks to [Stack Exchange](https://unix.stackexchange.com/questions/32588/grep-for-words-of-no-more-than-a-certain-length) for the guidance here. Once that’s good, as usual let’s `john <new-wordlist> hash.txt` and see if we get a match, and would you look at that? We got em.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZmQDm/23c5f676-edf4-4c77-998f-519ff1890bb4.jpg?source=viewer&v=82dfc8d979dddbe6f86de8e171e1e16a)

So the hash is bcrypt, “a password-hashing function… based on the Blowfish cipher… in 1999” — Wikipedia, [bcrypt](https://en.wikipedia.org/wiki/Bcrypt). Looks like it’s a more sophisticated hash type by using random salts for more complexity, crazy stuff.

## Task 1.5

For the last hash in Task 1, let’s crack `279412f945939ba78ce0758d3fd83daa`, a salty boy. And let’s switch up the cracking tool to `hashcat`.

Honestly, this hash stopped me right in the tracks, so shoutout to [LightOrithm for the help](https://lightorithm.gitbook.io/searchlight/crack-the-hash).

`echo` in the new hash, then run `hashcat -m 900 hash.txt <wordlist> -r .../best64.rule`, if you have another solution, feel free to reach out and let me know.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuxw185/f03da16f-78b7-4942-b95f-19e1eacbff12.jpg?source=viewer&v=ddebd3e2c5328a686ca3ce14f171d9bf)

## Task 2.1

Task 2, dam long hash `F09EDCB1FCEFC6DFB23DC3505A882655FF77375ED8AA2D1C13F640FCCC2D0C85`, so `echo <hash> > hash.txt` and let’s crack it. The instructions state “*You might have to start using hashcat here and not online tools. It might also be handy to look at some example hashes on [hashcats page](https://hashcat.net/wiki/doku.php?id=example_hashes) .”*

Run `hashcat -a 0 -m 1400 hash.txt <wordlist>` to crack this SAH256 hash.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/OAuj8AXd/7f8c86b2-8c77-4d40-9342-11312f473c6a.jpg?source=viewer&v=eceb108ea580fa66aff94356249a02a5)

## Task 2.2

Next up here’s hash `1DFECA0C002AE40B8619ECF94819CC1B`, so `echo <hash> > hash.txt` and use [Hash Type Identifier](https://hashes.com/en/tools/hash_identifier). There you’ll get `NTLM`, so search the hashcat’s [example page](https://hashcat.net/wiki/doku.php?id=example_hashes), `NTLM` uses the code 1000.

Run `hashcat -a 0 -m 1000 hash.txt <wordlist>` and you’ll see a cracked hash.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/E0uZy00Y/e47271d3-12bc-4c61-a3de-4dd25c4504ba.jpg?source=viewer&v=5f19c35cdfe679e2e3ce7e8516b86742)

## Task 2.3

Alright, alright, alright, here’s some of the hash `$6$aReallyHardSalt$6WKUTqzq...ZAs02.` but it’s too long to paste here. Since the `$` symbols, `nano hash.txt` but this time include a `:` and the salt after the hash. And `1800` is the code for `hashcat`, but be patient.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/rRuQmmJ4/14eacebd-2c4e-4c9e-97d2-a8bc37a38001.jpg?source=viewer&v=cdd641f62ce15d65f1f71cacc7276fb9)

“When using HashCat’s built-in SHA512Crypt module (1800), HashCat extracted the salt and the rounds from the hash and began cracking the password. Compared to other hashes this hash took longer to calculate each potential password, however eventually the password was cracked.” — [cyber-99.co.uk](https://cyber-99.co.uk/mesmerize/thm-crack-the-hash-ctf)

## Task 2.4

Okay, lucky last `e5d8870e5bdd26602cab8dbe07a942c8669e56d6` hash, use code `4510` and you’ve got it.

![](https://p146.p4.n0.cdn.getcloudapp.com/items/eDu700A0/055d6299-987b-482b-ae71-cf0073f9ef88.jpg?source=viewer&v=0a0775951d7b35279644e1b7df32751b)

This is days 56, 57and 58 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.