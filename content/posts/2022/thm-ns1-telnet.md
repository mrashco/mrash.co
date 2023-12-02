---
title: TryHackMe Network Services 1 Part 2 Telnet
author: Mr Ash
type: "post"
published: 2022-04-01
lastUpdated: 2022-11-05
url: "/tryhackme-network-services-1-part-2-telnet/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/X6uEA811/ca2bb580-911a-470e-888b-7dc659b133cc.png?v=04747f7feec9adfcc85650ca92b18e84
categories: Cyber
tags:
    - Hacking
    - TryHackMe
    - Networking
---

Welcome to TryHackMe Network Services Walkthrough Part 2, oh yeah! Let’s learn, then enumerate and exploit a variety of network services and misconfigurations, second up is telnet. Watch this Network Services Walkthrough for TryHackMe’s room, Part 2 Telnet.

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/_llaFR0354E?feature=oembed" title="TryHackMe Network Services 1 Part 2 Telnet" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ TryHackMe Network Services 1 Part 2 Telnet](https://www.happyscribe.com/?utm_source=embed-player&utm_term=e41dd55eff51408a9d95b18f998801c9 "TryHackMe Network Services 1 Part 2 Telnet was transcribed") -->

<!-- </div><div class="hs-embed" data-hide_video="true" data-id="e41dd55eff51408a9d95b18f998801c9" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style> -->

## Task 5 Understanding Telnet

Questions:

- What is Telnet? application protocol
- What has slowly replaced Telnet? ssh
- How would you connect to a Telnet server with the IP 10.10.10.3 on port 23? telnet 10.10.10.3 23
- The lack of what, means that all Telnet communication is in plaintext? encryption

## Task 6 Enumerating Telnet

Questions:

- How many ports are open on the target machine? 1
- What port is this? 8012
- This port is unassigned, but still lists the protocol it’s using, what protocol is this? tcp
- Now re-run the nmap scan, without the -p- tag, how many ports show up as open? 0
- Based on the title returned to us, what do we think this port could be used for? a backdoor
- Who could it belong to? Gathering possible usernames is an important step in enumeration. Skidy

## Task 7 Exploiting Telnet

Questions:

- Great! It’s an open telnet connection! What welcome message do we receive? SKIDY’S BACKDOOR.
- Let’s try executing some commands, do we get a return on any input we enter into the telnet session? (Y/N) N
- Now, use the command “ping \[local THM ip\] -c 1” through the telnet session to see if we’re able to execute system commands. Do we receive any pings? Note, you need to preface this with .RUN (Y/N) Y
- What word does the generated payload start with? mkfifo
- What would the command look like for the listening port we selected in our payload? nc -lvp 4444
- Success! What is the contents of flag.txt? THM{y0u\_\*\*\*\*\*\*\*\*\*\*}

{{<youtube _llaFR0354E>}}