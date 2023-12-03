---
id: 4964
title: TryHackMe Nmap Room Notes
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4964
url: "/?p=4964"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Are you going through TryHackMe’s Nmap Room? Did you forget to take notes? I got you covered. Here are my Nmap room notes from TryHackMe, use them as much as you need!

*Disclaimer, this is written in shorthand format, meaning, full sentences and proper grammar are always not used. For a full writeup, see [TryHackMe Nmap Walkthrough](https://mrash.co/tryhackme-nmap-walkthrough/), for help with Linux, see [Quick Start Guide](https://mrash.co/linux-quick-start-guide/).*

## Task 1 Deploy &amp; Task 2 Introduction

Ports: allow multiple network services, ensure correct device communication, 65535 total.

- Network connections between two ports:
    - one open on server,
    - one, high-numbered opens randomly on device.
- Port scanning: shows services running on target, “landscape”, `nmap` tool is used.
- Types of ports: (example standard ports: 443 HTTPS, 80 HTTP, 139 Win NETBIOS, SMB 445).
    - Well-known: 0-1023.
    - Registered: 1024 to 49151.
    - Dynamic/private: 49152 to 65535.
- Port states: open, closed, or filtered (from firewall).

## Task 3 Nmap Switches

Types of scans/switches:

- `-sS` TCP SYN.
- `-sU` UDP Scan.
- `-O` operating system.
- `-sV` version.
- `-v` or `-vv` increase verbosity.
- `-oA` output 3 major formats.
- `-oN` output normal format.
- `-oG` output grepable format.
- `-A` aggressive mode: services, OSs, traceroute, scripts.
- `-T<0-5>` timing, higher is faster.
- `-p` scan only specific port e.g. `-p 80`, `-p 1000-1500`
- `-p-` scan all ports.
- `--script` use script e.g. `--script=vuln`

## Scan Types – Task 4 Overview, Task 5 TCP Connect, Task 6 SYN, Task 7 UDP, Task 8 NULL, FIN and Xmas, Task 9 ICMP Network Scanning

Basic scan types:

- `-sT` TCP Connect: uses three-way handshake `SYN` &gt; `SYN/ACK` &gt; `ACK` – default without sudo priv.
    - If port closed `SYN` &gt; `RST` reset, If firewall `SYN >` blank/filtered/dropped.
- `-sS` SYN (half-open/stealth): `SYN` &gt; `SYN/ACK` &gt; `RST` – default with sudo priv.
    - Benefits: avoids older detections, often not logged, slightly faster.
    - Cons: sudo/root/admin privs, some services can brought down.
- `-sU` UDP: stateless connection, difficult/slower to scan.
    - Should be no response, assumed open, marked open/filtered, moves on.
    - If closed, should receive ICMP (ping) packet.

Less common scan types: used for firewall evasion.

- `-sN` TCP Null: sends empty packet, no `SYN` flag.
- `-sF` TCP Fin: sends almost empty packet, only `FIN` flag, used to close active connection.
- `-sX` TCP Xmas: sends `URG` (Urgent), `PUSH`, and `FIN` flags, looks like chirstmas tree in wireshark.

ICMP Network Scanning: find map/landscape, scans any port

- `-sn <ip range>` find up/down hosts e.g. `192.168.0.1-254` or `192.168.0.0/24`
- Forces ICMP or ARP (local networks).

I hope this has helped you, if it has, feel free to subscribe to my newsletter, that would mean heaps!

This is Day 39 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, follow my [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.