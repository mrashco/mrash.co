---
id: 4674
title: "Hashing Passwords \u2022 Python Module Basics"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4674
url: "/?p=4674"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Hashing-Passwords--Python-Module-Basics-e18s525" width="400px"></iframe>Interested in learning about hashing passwords? How do programs hash? What is hashing?

Hashing is the foundation of tech like blockchains that make cryptocurrencies possible. See [Blockchain 101 – A Visual Demo](https://youtu.be/_160oMzblY8) and [Blockchain 101 – Part 2 – Public / Private Keys and Signing](https://youtu.be/xIDL_akeras).

So for a fun study session, let’s follow a walkthrough on Password Hashing in Python, see the [original post](https://replit.com/talk/learn/Hashing-Passwords/146310) by [DillonB07](https://replit.com/@DillonB07).

Watch live video:

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/3TSiiWzgmTE?feature=oembed" title="Hashing Passwords Python • Beginner Python Learning Replit Tutorial • Study Session #1 (LoFi Chill)" width="800"></iframe></div></figure>*Disclaimer, this is not my original work, see links for more details. For a python guide, see [Intro to Python](https://mrash.co/intro-to-python-free-python-starter-guide/).*

## 1. Update Python and Pip

Update both pip and Python before starting this program. Either open PowerShell or do it via vscode terminal:

```
<pre class="wp-block-code">```
C:\\<path to program>\\python.exe -m pip install --upgrade pip

```
```

Optionally uninstall Python via Control Panel and reinstalled via [Python.org](https://www.python.org/downloads/), or do it via command line too.

## 2. Import Werkzeug “Tool” Module

Importing modules is very simple in Python.

```
<pre class="wp-block-code">```
from werkzeug.security import generate_password_hash, check_password_hash

```
```

I’m familiar with `import` being the command, I need to do more reading up on `from` to better understand why some modules need this over others.

This is what gave me all the issues, couldn’t use the werkzeug module, after a while, just a simple update fixed this.

## 3. Generate Password Hash

Let’s use `generate_password_hash` to convert a string inside a variable to a SHA256 hash.

```
<pre class="wp-block-code">```
password = 'hello world'
hashword = generate_password_hash(password, 'sha256')
print(f'1: {hashword}')
password1 = 'hello world'
hashword1 = generate_password_hash(password, 'sha256')
print(f'2: {hashword}')

```
```

Also, this is using f strings, something else I need to read up on.

## 4. Check Password Hash

Lastly, use check\_password\_hash to receive a Boolean value of True or False when comparing passwords.

```
<pre class="wp-block-code">```
checked = check_password_hash(hashword, password1)
print(checked)

```
```

This also confused me a bit, my hashes were not exactly the same as the example. I’m not sure if the module has changed or I did something wrong.

## 5. Reflection

This was a great little project to explore while learning Python. Replit, the software I use to run and embed Python programs has an amazing community.

I’m absolutely loving scrolling through their user tutorials to find well-written guides and posts.

While watching Twitch, I was also inspired to record the full process of writing code. Something I’m terrified of! Recording myself and putting it out there is hard, but this was a nice introduction to it.

I’m going to hit record more in the future and share the work! I think giving people the opportunity to watch the entire process is exciting.

This is Day 23 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.