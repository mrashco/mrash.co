---
id: 4781
title: Kali Linux WSL WITHOUT Microsoft Store
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4781
url: "/?p=4781"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Kali-Linux-WSL-WITHOUT-Microsoft-Store-e16jqbl" width="400px"></iframe>Before you start, make sure your Windows 10 OS is up to date as version 1903 or higher can run this. To check the version, click `Windows Start Button` and type `System Information`, next to Version you’ll see your current number.

If lower than version 1903, go to `Settings` and `Update` to get latest changes.

Okay, now you’re good to go!

## 1. Setup Subsystem for Linux

Right click `Windows Start Button` and open `Windows PowerShell (Admin)`. Copy/paste:

```
<pre class="wp-block-code">```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

```
```

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/6qu8z1bB/8f9f4608-ac82-4471-b5d7-bc63c044ac48.png?v=c18fd8410f0af0f28afc0cd0d1625703](https://p146.p4.n0.cdn.getcloudapp.com/items/6qu8z1bB/8f9f4608-ac82-4471-b5d7-bc63c044ac48.png?v=c18fd8410f0af0f28afc0cd0d1625703)</figure></div>Then copy/paste:

```
<pre class="wp-block-code">```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

```
```

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/4gu2XkBW/215f5cdd-ae70-477b-8716-65331804fe9a.png?v=845fc3b3b1ef8806a0c405c569e75e2a](https://p146.p4.n0.cdn.getcloudapp.com/items/4gu2XkBW/215f5cdd-ae70-477b-8716-65331804fe9a.png?v=845fc3b3b1ef8806a0c405c569e75e2a)</figure></div>If you have any issues or need more info, see [Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

## 2. Download Kali Linux .appx file

Click [this link](https://aka.ms/wsl-kali-linux-new) to start download of Kali Linux. \[<https://aka.ms/wsl-kali-linux-new>\]

May take a couple of minutes depending on your internet speed.

Once downloaded, run file to install.

<div class="wp-block-image"><figure class="alignleft is-resized">![https://p146.p4.n0.cdn.getcloudapp.com/items/z8u6bNeJ/a40254fa-9a30-432e-9a2a-5bbaa327ddf1.png?v=4950a902523a3f61c67e9c71429a898e](https://p146.p4.n0.cdn.getcloudapp.com/items/z8u6bNeJ/a40254fa-9a30-432e-9a2a-5bbaa327ddf1.png?v=4950a902523a3f61c67e9c71429a898e)</figure></div>For any other Linux distro, see [Manually download Windows Subsystem for Linux distro packages](https://docs.microsoft.com/en-us/windows/wsl/install-manual).

## 3. Setup Kali

Great! Now Kali Linux is installed via WSL, now setup your username and password.

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/v1ubWdw2/79ff1fec-1c35-4525-b6c1-5cbf75e37c19.png?v=bfc9fcc2788381a735c97da247465ba6](https://p146.p4.n0.cdn.getcloudapp.com/items/v1ubWdw2/79ff1fec-1c35-4525-b6c1-5cbf75e37c19.png?v=bfc9fcc2788381a735c97da247465ba6)</figure></div>I recommend also running `sudo apt update && upgrade` to ensure all packages are current.

If you have feedback, please send me a message via [Twitter](https://twitter.com/mrashleyball).

This is Day 7 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) and see the journey!

Happy Hacking.