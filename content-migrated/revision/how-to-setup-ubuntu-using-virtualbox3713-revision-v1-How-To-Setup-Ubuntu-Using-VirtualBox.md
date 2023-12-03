---
id: 4786
title: How To Setup Ubuntu Using VirtualBox
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4786
url: "/?p=4786"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/How-To-Setup-Ubuntu-Using-VirtualBox-e16jqn4" width="400px"></iframe>Setting up a Linux Operating System like Ubuntu can be a bit daunting, especially if you’re a firm Windows user with no Linux experience.

I’m glad you’re here starting your Linux journey! You won’t look back!

Ubuntu is generally accepted as the most beginner-friendly Linux OS.

## 1. Download Ubunutu &amp; VirtualBox

Go to [ubuntu.com](https://ubuntu.com/download/desktop) to download the iso file, it has the entire operating system compressed into it.

Note the system requirements:

- 2 GHz dual-core processor or better.
- 4 GB system memory.
- 25 GB of free hard drive space.

Your computer, aka host machine, will need to be above these to share resources with your Virtual Machine (VM). Why? You’ll run into a sluggish experience otherwise i.e. not enough juice in the tank!

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/kpuKkqKv/7bb6ceda-f5a2-4b31-bbbb-2d9034d00012.png?v=29c3382ceb14467cb9fa96827777e0ec](https://p146.p4.n0.cdn.getcloudapp.com/items/kpuKkqKv/7bb6ceda-f5a2-4b31-bbbb-2d9034d00012.png?v=29c3382ceb14467cb9fa96827777e0ec)</figure></div>Now grab [VirtualBox](https://www.virtualbox.org/wiki/Downloads) for your current operating system (Windows, macOS or Linux) on your computer, I’ll be using Windows.

You don’t have to read all of it, but it’s good to know the [VirtualBox User Manual](https://www.virtualbox.org/manual/UserManual.html) has everything you need in case you run into issues.

<div class="wp-block-image"><figure class="alignleft">![https://p146.p4.n0.cdn.getcloudapp.com/items/xQublX7Z/17b5664e-7bac-4bf1-828c-1ce47d673cce.png?v=78460783551cc60cabd832e18b7ec6ef](https://p146.p4.n0.cdn.getcloudapp.com/items/xQublX7Z/17b5664e-7bac-4bf1-828c-1ce47d673cce.png?v=78460783551cc60cabd832e18b7ec6ef)</figure></div>Once downloaded, install VirtualBox by running the .exe file.

## 2. Virtual Machine Settings

Let’s get Ubuntu installed:

1. Click new (the blue startup top) and name your VM, I recommend a logical naming convention like Ubuntu 1 and creating a new folder with the same name.
2. Put it wherever you’d like, but I’d also recommend creating a VM root folder for any other VM you create.
3. VirtualBox should detect what type and version depending on the name you give it. If it isn’t correct, use the drop-down options to select Linux and Ubuntu (64-bit). ![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuwkLqE/cd3aeda9-0af9-498b-8b2c-d64dc193eaf5.jpeg?v=e45b5c47f112e8050c1345864cf68789](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuwkLqE/cd3aeda9-0af9-498b-8b2c-d64dc193eaf5.jpeg?v=e45b5c47f112e8050c1345864cf68789)
4. Set the Memory size, remember what the system requirements were? 4GB, so type 4000MB into the input field. ![https://p146.p4.n0.cdn.getcloudapp.com/items/YEuRj9Zk/50b7b120-d8b1-4075-befe-7efaf8e7c816.jpeg?v=a2a8dfe10526dc9d2b89c65a07352bc0](https://p146.p4.n0.cdn.getcloudapp.com/items/YEuRj9Zk/50b7b120-d8b1-4075-befe-7efaf8e7c816.jpeg?v=a2a8dfe10526dc9d2b89c65a07352bc0)
5. Select Create in the Hard disk section, we don’t need to change anything here, press Next.
6. VDI is fine for the Hard disk file type, select Next.
7. Read the difference between Dynamically allocated and Fixed-size, I recommend Dynamic.
8. Now for File location and size leave the file path default and scale up the size to at least 25GB to fit system requirements.

## 3. Insert Ubuntu ISO File

Great! Now your VM is ready to boot… or is it??

1. If you hit Start a warning dialogue box should appear: ![https://p146.p4.n0.cdn.getcloudapp.com/items/12uABnvN/9d84b068-dab7-43ec-867a-ca1674784c47.png?v=a314274266c53d7433db97b80bb89644](https://p146.p4.n0.cdn.getcloudapp.com/items/12uABnvN/9d84b068-dab7-43ec-867a-ca1674784c47.png?v=a314274266c53d7433db97b80bb89644)
2. This is where you select the Ubunutu iso file from back in step 1. Click the folder with the green up arrow &gt; Add &gt; navigate to iso file. ![https://p146.p4.n0.cdn.getcloudapp.com/items/bLuA8nqR/ca7a7754-e4c9-409a-805d-3223ab4237ed.png?v=c9aa1204bc09f7683f40a6a27b93edf1](https://p146.p4.n0.cdn.getcloudapp.com/items/bLuA8nqR/ca7a7754-e4c9-409a-805d-3223ab4237ed.png?v=c9aa1204bc09f7683f40a6a27b93edf1)
3. If the VM starts up and fails, close window &gt; power off the machine. ![https://p146.p4.n0.cdn.getcloudapp.com/items/QwuE6m5k/26b8ec3c-207d-4dd0-80fa-83b1daf2bdf6.png?v=849767160a3cd629c1821cb7249a4547](https://p146.p4.n0.cdn.getcloudapp.com/items/QwuE6m5k/26b8ec3c-207d-4dd0-80fa-83b1daf2bdf6.png?v=849767160a3cd629c1821cb7249a4547)
4. Now under the VM Storage settings, click \[Optical Drive\] Empty and follow step 2 above.

Now follow your nose from here, watch the prompts and check the settings, it’s straightforward.

## 4. Setup Guest Additions

Once your new Ubuntu VM is set up and ready to rock, it’s recommended to install [VirtualBox’s Guest Additions](https://www.virtualbox.org/manual/UserManual.html#guestadditions). It’s optional software that gives some ‘nice to have features to make life easier.

To install, within VirtualBox select Devices (up the top of VM) &gt; Insert Guest Additions CD image…

So now you’re set up and good to go! Thanks for reading and I hope this walkthrough has been easy to follow and helpful. If you have feedback, please send me a message via [Twitter](https://twitter.com/mrashleyball).

This is Day 1 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my weekly newsletter to see the learning journey!

Happy Hacking.