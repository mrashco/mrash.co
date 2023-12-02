---
title: TryHackMe Network Services 1 Part 3 FTP
author: Mr Ash
type: "post"
published: 2022-04-01
lastUpdated: 2022-11-04
url: "/tryhackme-network-services-1-part-3-ftp/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/7KuQoq6z/9521607b-6f11-47fb-b34d-069e6f1a6657.png?v=3a85647cebcc7d2cdbef482741493f4e
categories: Cyber
tags:
    - Hacking
    - Linux
    - Networking
---

Let’s go, TryHackMe Network Services Walkthrough Part 3, welcome! Step 1 learn, step 2 enumerate, and step 3 exploit… but what? Well, a variety of network services and misconfigurations of course, this time it’s FTP. Watch the Network Services Walkthrough for TryHackMe’s room, Part 3 FTP.

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/lpjifLzyX8Q?feature=oembed" title="TryHackMe Network Services 1 Part 3 FTP" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important"> -->

<!-- </div><div class="hs-embed" data-hide_video="true" data-id="c9f0b31784d84e14b0f77b48ea9339ff" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style> -->

## Task 8 Understanding FTP

Questions:

- What communications model does FTP use? client-server
- What’s the standard FTP port? 21
- How many modes of FTP connection are there? 2

## Task 9 Enumerating FTP

Questions:

- How many ports are open on the target machine? 2
- What port is ftp running on? 21
- What variant of FTP is running on it? vsftpd
- What is the name of the file in the anonymous FTP directory? PUBLIC\_NOTICE.txt
- What do we think a possible username could be? mike

## Task 10 Exploiting FTP

Questions:

- What is the password for the user “mike”? password
- What is ftp.txt? THM{y0u\_\*\*\*\*\*\*\*\*\*\*\*\*\*\*}

{{<youtube lpjifLzyX8Q>}}