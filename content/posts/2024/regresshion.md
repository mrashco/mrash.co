---
title: RegreSSHion (2006's OpenSSH Vuln is Back Again)  
published: 2024-07-03T14:42:26+10:00
# lastUpdated: 2024-07-03T14:42:26+10:00
url: regresshion
description: "" # Prompt: Write an SEO description for the blog post Regresshion. Keep it 320 characters or less, use the title exactly as is once.
aliases: # Use aliases for multiple
    - regresshion-cve-2024-6387
    - cve-2024-6387-openssh-vuln

cover:
    image: "https://i.imgur.com/PElwgB3.png"
    # alt: "ALT_TEXT"
    # caption: "CAPTION_TEXT"
    relative: false # To use relative path for cover image, used in hugo Page-bundles 

type: post # post, letter, note, page
categories: zero-day # Homelab, Writeup, Personal
tags: # Prompt: Write 10 tags for Regresshion in YAML format, use code block 
    - cve-2024-6387
    - regresshion
    - openssh-vulnerability
    - ssh-vulnerability
    - regression-analysis
    - security-patch
    - vulnerability-exploit
    - cve-tracking
    - open-source-security
    - information-security

draft: false

# ShowToc: false
# TocOpen: false

# searchHidden: true # Make false to hide page from search
---

<!-- ## RegreSSHion (2006's OpenSSH Vuln is Back Again)   -->

### OpenSSH Zero-Day Vulnerability (CVE-2024-6387)
- A new zero-day vulnerability, "RegreSSHion", allows Remote Code Execution (RCE) with root privileges due to a signal handler race condition.
- This regression of CVE-2006-5051 was inadvertently reintroduced in an update. An attacker can exploit it by repeatedly connecting without authenticating, aiming for a precise timing window. Versions 4.4p1 and earlier

## Detection and Mitigation
- Oligo ADR can detect abnormal behaviour, including exploitation attempts.
- Prioritize patching or using workarounds on OpenSSH servers running on glibc-based Linux systems to mitigate this high-risk vulnerability.

### Disabling LoginGraceTime to Mitigate
1. Open `/etc/ssh/sshd_config` (or equivalent) in your editor.
2. Find the `LoginGraceTime` option; add it if it's not present.
3. Set its value to 0 to disable the timeout.

## FAQs
### What's signal handler race condition?
- A signal handler race condition occurs when multiple processes or threads access shared resources while using signals for communication, leading to bugs.
- In OpenSSH's CVE-2024-6387 vulnerability, the SIGALRM signal handler closes connections if clients fail to authenticate within a set time. However, it mistakenly executes unsafe functions like syslog() in an asynchronous context.
- An attacker can exploit this by repeatedly attempting to connect without authenticating, aiming to trigger the signal handler during vulnerable operations and potentially gain root privileges through heap corruption and code execution.

### What are glibc-based Linux systems?
- The GNU C Library (glibc) is the standard C library for the GNU operating system and most Linux distributions, providing core functions for memory allocation, string manipulation, and input/output operations.
- When referring to "glibc-based Linux systems", it means systems that use glibc as their primary C library implementation. Examples include Ubuntu, Debian, Red Hat Enterprise Linux, CentOS, and others. 
- In the context of CVE-2024-6387, administrators should prioritize patching or using workarounds on OpenSSH servers running on these glibc-based systems to mitigate this high-risk vulnerability.

Resources 
- https://www.oligo.security/blog/critical-openssh-vulnerability-cve-2024-6387-regresshion
- https://www.qualys.com/2024/07/01/cve-2024-6387/regresshion.txt
- https://systemweakness.com/understanding-the-critical-openssh-vulnerability-cve-2024-6387-regresshion-533062396346
- https://github.com/ikhaleelkhan/cve-2024-6387-poc