---
id: 5498
title: Learning HTTP Requests &#8211; A Mini HTTP Exercise
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5498
url: "/?p=5498"
---

While learning [HTTP in Detail](https://tryhackme.com/room/httpindetail), I thought it’d be fun to put it to the test in the terminal.

Here’s a quick exercise to practice learning HTTP Requests, Responses and Headers.

- **Difficulty:** Easy – new to Linux.
- **Environment**: local Debian-based Linux installation e.g. [Ubuntu in VirtualBox](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/).
- **Commands**: `git`, `python3`, `cd`, `mkdir`, `wget`.

## Steps

Here’s everything you need to do, note, you’ll need two terminals to do this:

1. Terminal 1: `git clone https://github.com/mrashleyball/HTTP.git`, `cd HTTP`
2. `python3 -m http.server`
3. Terminal 2: `nc 0.0.0.0 8000`, `GET / HTTP/1.1`
4. `nc 0.0.0.0 8000`, `GET /flag.txt HTTP/1.1`
5. `mkdir Downloads`, `cd Downloads`
6. `wget 0.0.0.0:8000`, `wget 0.0.0.0:8000/flag.txt`

Wow, pretty easy to spin up web servers and test HTTP Requests, hey?

## Explanation

This is a good exercise to take a step beyond the theory, TryHackMe does a great job with interactive static web pages within their platform.

But I thought it’d be fun to go one step further and test it out within the terminal.

Using the python webserver with netcat, you can clearly see the request making it to the server and it responds with the `index.html` file, very cool.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/7KuQnzg6/32afd2e5-d1d2-45b8-9e70-6f6cddccb37d.jpeg?v=02e071e63c51d47eaaecca3f5e5f40d4](https://p146.p4.n0.cdn.getcloudapp.com/items/7KuQnzg6/32afd2e5-d1d2-45b8-9e70-6f6cddccb37d.jpeg?v=02e071e63c51d47eaaecca3f5e5f40d4)</figure>And for the `flag.txt` you simply need to specify the file path to get the response:

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/rRu1BgPb/5bcd68ab-a90a-4001-8a4d-2690d616ceb3.jpeg?v=3a1d02039587da30a671942a5932959c](https://p146.p4.n0.cdn.getcloudapp.com/items/rRu1BgPb/5bcd68ab-a90a-4001-8a4d-2690d616ceb3.jpeg?v=3a1d02039587da30a671942a5932959c)</figure>For more help, here’s a list of links to helpful guides/articles/forums I used in my research:

- [HTTP in detail – How the web works](https://youtu.be/XZyapIKV3Rw)
- [Networking Fundamentals – Practical Networking](https://www.youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi)
- [How to make an HTTP GET request manually with netcat?](https://stackoverflow.com/questions/32341518/how-to-make-an-http-get-request-manually-with-netcat/32341614)
- [Using nc (netcat) to make an HTTP request](https://osric.com/chris/accidental-developer/2018/01/using-nc-netcat-to-make-an-http-request/)
- [How to Remove a Directory in Linux](https://phoenixnap.com/kb/remove-directory-linux) – `rm -rf <dir>` (if you forget like me)

## Reflection

This was a really fun little exercise to think up and put together, I love doing mini-projects like this. It combines all the skills I believe are important in tech like writing, teaching and having a grasp on the fundamentals.

“It is important to view knowledge as sort of a semantic tree — make sure you understand the fundamental principles, ie the trunk and big branches, before you get into the leaves/details or there is nothing for them to hang on to.” – [Elon Musk](https://lifehacker.com/elon-musk-on-learning-new-things-view-knowledge-as-a-t-1677850415).

Thanks for reading and I hope you learned something from this little exercise. This is day 47 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.

<figure class="wp-block-embed is-type-rich is-provider-twitter wp-block-embed-twitter"><div class="wp-block-embed__wrapper">> While learning [\#HTTP](https://twitter.com/hashtag/HTTP?src=hash&ref_src=twsrc%5Etfw) via [@RealTryHackMe](https://twitter.com/RealTryHackMe?ref_src=twsrc%5Etfw) I put together a little HTTP exercise to see if I understood what the hell is going on… turns out I sort of do!<https://t.co/d0CDOsCwtc>
> 
> — Mr Ash (@mrash\_co) [April 21, 2022](https://twitter.com/mrash_co/status/1516972769766158337?ref_src=twsrc%5Etfw)

<script async="" charset="utf-8" src="https://platform.twitter.com/widgets.js"></script></div></figure>