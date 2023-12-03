---
id: 5879
title: 'OverTheWire: Bandit'
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5879
url: "/?p=5879"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Bandit is a beginner Capture The Flag (CTF) game from OverTheWire (OTW).

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/JjiG4CYxXgw?feature=oembed" title="OverTheWire Bandit Walkthrough | Beginner Capture The Flag (CTF) Guide | OTWBandit Level 0 - 4" width="800"></iframe></div></figure>Whether you’re familiar with text-based games or have never even thought of playing them (me). This is the perfect CTF for learning Linux.

You’re here to either copy my answers OR learn. Can I ask you to please focus on the learning? It’s okay to peak when you’re so blind it’s crippling you, but please don’t just copy, copy, copy!

Take the time to try, fail and repeat. It’s a massive part of learning. Don’t rob yourself of that.

One more thing before we go any further. Open something to take notes in, Notion, Text Editor, heck Mircosoft Word. It doesn’t matter. But it’s a great idea to record what you’ve done and how you’ve done it.

Okay, lecture over. Let’s CTF!!

## Level 0 – Level 4

<figure class="wp-block-image size-large">![](https://p146.p4.n0.cdn.getcloudapp.com/items/Kou1jmn8/832a98ae-411b-4316-a3ab-cf3679bc0722.jpg?v=bd4f8a2ed7361125adc37f9d90b3b5c1)</figure>### Level 0

Okay, let’s get started with Bandit Level 0 and connect to the game via Secure Socket Shell (SSH).

This tells Linux to run the `ssh` command, connect to `bandit.labs.overthewire.org` via port `2220` and user `bandit0`. So all together it looks like `ssh bandit0@bandit.labs.overthewire.org -p 2220`.

Then, type `yes` and hit `enter` to complete the connection.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXg7g/dec86188-5f56-427a-b6d9-ee1464f7c2d9.jpeg?v=1c7e58bc8f158f35f19a88e1158ba2b4](https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXg7g/dec86188-5f56-427a-b6d9-ee1464f7c2d9.jpeg?v=1c7e58bc8f158f35f19a88e1158ba2b4)</figure>Take a moment to read the rules and check out the welcome message.

### Level 1

Okay, now put your game face on *grunts*.

Let’s take a look at our goal. *The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.*

I like to copy/paste the goal into my note-taking app and highlight/bold areas that are important. In this case, we’ve got clear instructions to find the readme file.

Okay, let’s look around the machine, find the file and then read it. We’ll use the `ls` command to view files in the current directory. Then we’ll `cat` the file we find.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Qwudn6yR/39e5cf9c-7968-4fc9-b187-46b5b1c9e918.jpeg?v=93b597186a271672468447deeb808f9c](https://p146.p4.n0.cdn.getcloudapp.com/items/Qwudn6yR/39e5cf9c-7968-4fc9-b187-46b5b1c9e918.jpeg?v=93b597186a271672468447deeb808f9c)</figure>Great! We got it! I know it’s a random bunch of letters and numbers but in this CTF the “flags” will look like this. Other games might be a bit different, but this unreadable nonsense is a good thing!

Don’t forget to copy that flag by highlighting it and pressing `CTRL + SHIFT + C`.

Let’s confirm this is correct by cutting the connection via `bandit0` user and `ssh` into the next level via `bandit1`. We’ll do that by running the command `exit`.

Now instead of typing or copying/pasting the `ssh` credentials, let’s use the `up` arrow to find our last command. Edit the command to make it more usable moving forward. Remove `bandit0@` in the beginning and add `-l bandit1`. All together, it looks like `ssh bandit.labs.overthewire.org -p2220 -l bandit1`

Now paste the flag using `CTRL + SHIFT + V` which you can copy from your notes because you’re definitely taking notes, right??? Done with Bandit Level 1, so move on to the next level.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>### Level 2

Alrighty, now it’s getting serious with Bandit Level 2. First things first, let’s read that goal. *The password for the next level is stored in a **file** called **–** located in the home directory*

Okay, seems easy, same as last round, `ls` then `cat`…right?

Try it, but you’ll see the issue. We need to specify the exact file path in order for Linux to understand. We’ll add `./` which tells Linux “hey, I’m in this folder”.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6JrN/0b40a03c-844c-4a1a-9529-6378b9d1678b.jpeg?v=6726588a209f627ca2a96dc218d1e0d7](https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6JrN/0b40a03c-844c-4a1a-9529-6378b9d1678b.jpeg?v=6726588a209f627ca2a96dc218d1e0d7)</figure>That looks pretty good, so let’s follow the same process of `exit` &gt; `up` &gt; change user, in this case, `bandit2` &gt; and paste the flag as the password.

### Level 3

Training wheels are off, quick goal check. *The password for the next level is stored in a **file** called **spaces in this filename** located in the home directory.*

Okay, hm, a bit unusal. This shouldn’t be too difficult… shouldn’t be.

If we try and `cat` out to see the file, but type out `spaces in this filename` it treats each word as a separate file. How do we fix this?

After a bit of googling… it’s quite easy. Just add a `\\` after each word. But to make it easier, hit `TAB` after typing the first letter `s` and it’ll do it for you!

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/2Nu7mkO1/22647bce-145a-4550-9cab-c2baee6186b6.jpeg?v=e9c9258f7e857c537e0218e0a6bfb5f1](https://p146.p4.n0.cdn.getcloudapp.com/items/2Nu7mkO1/22647bce-145a-4550-9cab-c2baee6186b6.jpeg?v=e9c9258f7e857c537e0218e0a6bfb5f1)</figure>Flag, got, nice, thanks Bandit Level 3. Now get out of this level and move on to the next one.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>### Level 4

Let’s go beyond `ls` and `cat` and start changing the directory (aka folders).

So what’s the goal? *The password for the next level is stored in a hidden file in the **inhere** directory.*

Okay, our clue is the directory is hidden, tuck that away for now. Let’s view what’s around and move into our directory using `cd`. You might notice I’m using `&&` to chain commands together, a neat little trick I’ve picked up. So try `cd inhere && ls` and we should see our file but it’s hidden.

We need to introduce flags, these are like switches we can use to add features to our programs.

`ls` displays files, but if we turn on `-a` it will also display hidden files. Let’s try it!

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Kou1jmbQ/616bf51e-7a5c-499d-9993-14d139643342.jpeg?v=4507daf489634fb74c775d9728a648e7](https://p146.p4.n0.cdn.getcloudapp.com/items/Kou1jmbQ/616bf51e-7a5c-499d-9993-14d139643342.jpeg?v=4507daf489634fb74c775d9728a648e7)</figure>Nice! We got the flag for Bandit Level 4, nice. Now let’s exit and move on to the next level in [Bandit Levels 5 to 9](https://mrash.co/bandit-level-5-level-9/).

Thanks for reading and I hope you learned something from this little exercise. This is days 4 and 56 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.

## Bandit Level 5 – Level 9

<figure class="wp-block-image size-large">![](https://p146.p4.n0.cdn.getcloudapp.com/items/o0uXZXnv/9588388a-5d0b-4842-8834-33486290deb4.jpg?v=e56463c3ab15deb00b445da01340de0e)</figure>Welcome to another instalment of the Bandit CTF series!

This is the best way to learn Linux, BASH, terminals, commands and everything in between!

Let’s `ssh` in to Bandit:

```
<pre class="wp-block-code">```
$ ssh bandit.labs.overthewire.org -p 2220 -l bandit5

```
```

You’ll need the password from the previous level.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/xGQXj5MAVss?feature=oembed" title="Bandit Level 5 - 9 OverTheWire Walkthrough | Capture The Flag Guide | Bandit Levels 5 to 9" width="800"></iframe></div></figure>### Level 6

Let’s get started by `ls -la` and see what we have.

```
<pre class="wp-block-code">```
total 24
drwxr-xr-x  3 root root    4096 May  7  2020 .
drwxr-xr-x 41 root root    4096 May  7  2020 ..
-rw-r--r--  1 root root     220 May 15  2017 .bash_logout
-rw-r--r--  1 root root    3526 May 15  2017 .bashrc
drwxr-x--- 22 root bandit5 4096 May  7  2020 **inhere**
-rw-r--r--  1 root root     675 May 15  2017 .profile

```
```

Ah, let’s go into the `inhere` directory via `cd inhere && ls -la`.

Using the `&&` lets us stack together a series of commands, this way we 1) change directories and 2) list out the files in the new directory all at once, so cool!

```
<pre class="wp-block-code">```
total 88
drwxr-x--- 22 root bandit5 4096 May  7  2020 .
drwxr-xr-x  3 root root    4096 May  7  2020 ..
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere00
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere01
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere02
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere03
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere04
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere05
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere06
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere07
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere08
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere09
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere10
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere11
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere12
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere13
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere14
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere15
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere16
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere17
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere18
drwxr-x---  2 root bandit5 4096 May  7  2020 maybehere19

```
```

…wow! We’ve got a lot of directories to search through now…

Hmm, there must be a better option to automatically search these folders! Enter the `find` command, with it we can search multiple directories and pass it certain switches to narrow down our results, let’s test it out.

```
<pre class="wp-block-code">```
$ find .

```
```

This runs `find` in the current directory, that’s what the `.` is for.

We can be more specific and use switches like `-type` or `-size` to find exactly what we’re looking for.

Let’s go back and get a clue from [Bandit Level 5 → Level 6](https://overthewire.org/wargames/bandit/bandit6.html):

*The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:*

*human-readable 1033 bytes in size not executable*

Okay, so we’ve got some hints for what file we’re trying to find. Let’s use the `-size` switch with the byte size and see what we get.

```
<pre class="wp-block-code">```
$ find . -size 1033

```
```

That’s weird, no luck! That’s because we need to specify what file size exactly, 1033 is just a number. Let’s search it up!

Thanks to [linuxconfig.org](https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size) we know we need to use `c` for bytes.

\*Don’t forget to use the up arrow to see last command!

```
<pre class="wp-block-code">```
$ find . -size 1033c
./maybehere07/.file2

```
```

Cool, look at that! Now we have only one search result, let’s see if we can `cat` it out and view it.

```
<pre class="wp-block-code">```
$ cat ./maybehere07/.file2
banditflag5-6{*****}

```
```

We got it! Now `exit` out and let’s go again!

\*Since my first few writeups I’ve learnt sharing flag’s isn’t the best idea as it allows anyone to simply copy/paste their way through without trying or trying.

### Level 7

Let’s jump into the next one head first and see what we get!

```
<pre class="wp-block-code">```
$ ls -la

```
```

Okay, strange, nothing there. Maybe I should read the goal first after all!

*The password for the next level is stored somewhere on the server and has all of the following properties:*

*owned by user bandit7 owned by group bandit6 33 bytes in size*

Ah, so the file isn’t within the `bandit6` directory, it’s somewhere else. No worries, let’s look up how to use the `find` command to get the right switches.

```
<pre class="wp-block-code">```
$ find --help

```
```

After looking a bit at the wall text, I see `-user NAME` and `-group NAME`, I think they’re what we’re after. We’ll use it with `-size` from the last level too.

```
<pre class="wp-block-code">```
$ find -user bandit7 -group bandit6 -size 33c

```
```

No luck! What did we forget?

The location! Currently, we haven’t specified where to look, remember it’s hidden anywhere on the server.

```
<pre class="wp-block-code">```
$ find / -user bandit7 -group bandit6 -size 33c

```
```

Good, it’s working! Bad there’s so many files we don’t have access to, how do we only see accessible files? One way is to remove the errors, as ‘Permission denied’ is an error, we can redirect those results elsewhere.

Thanks to [cyberciti.biz](https://www.cyberciti.biz/faq/unix-linux-redirect-error-output-to-null-command/) for explaining `stdin`, `stdout` and `stderr`, it’s worth reading over that aritcle to understand more.

```
<pre class="wp-block-code">```
$ find / -user bandit7 -group bandit6 -size 33c **2>/dev/null**
/var/lib/dpkg/info/bandit7.password

```
```

How cool? We got one search result, that makes life a lot easier.

The `2>/dev/null` may seem very strange at first. The `2` stands for `stderr` which is the errors we have as a result of our search. The `>` redirects and the `/dev/null` is a nothing space directory we can dump everything.

So, `cat` that sucker and grab your flag!

```
<pre class="wp-block-code">```
$ cat /var/lib/dpkg/info/bandit7.password
banditflag6-7{*****}

```
```

### Level 8

Let’s not read the instructions just yet! `ls` away my friends!

Ah, a simple `data.txt` file, this seems too easy to be real.

Let’s `cat` and …oh gosh… so much data, so much!

Hm, maybe we’ll go back to the hints now:

*The password for the next level is stored in the file **data.txt** next to the word **millionth.***

Okay, so we need to somehow search within the file and output the flag. Our only hint we have is it’s next to the word millionth.

`grep` is the command for the job, it searches for patterns in a file.

Let’s run `grep --help` to get familiar with it, we’re looking for a switch that’s simple enough to match our word with it. Let’s try `-e` or `-regexp=PATTERN`, that should do it!

```
<pre class="wp-block-code">```
$ grep data.txt -e millionth
banditflag7-8{*****}

```
```

Would you look at what we have here… a flag!

Let’s `exit` out and head over the next level!

### Level 9

Same as always, `ls` and see what we’re working with.

Looks like another `data.txt` file with even more ‘hard to read’ text.

Back to the [instructions](https://overthewire.org/wargames/bandit/bandit9.html):

*The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.*

We could use `grep` and put together a long `regex` to output what we need, but I’m not a wizard.. so we’ll be using `sort` and `uniq`.

First, let’s understand `sort` it’s similar to `cat` but run it against the `data.txt` and see the difference.

```
<pre class="wp-block-code">```
$ sort data.txt

```
```

Everything is sorted, cool.

But how do we then find the unique flag? `uniq` of course.

Try it:

```
<pre class="wp-block-code">```
$ uniq data.txt

```
```

Hm, that didn’t work… that’s because we need to use them together. Since they’re separate commands, we’ll use the `|` pipe to chain it together.

```
<pre class="wp-block-code">```
$ sort data.txt | uniq

```
```

Still no luck, let’s run `uniq --help` and see if there’s a switch that can help.

Yep! `-u` which only prints unique lines, that sounds perfect!

```
<pre class="wp-block-code">```
$ sort data.txt | uniq - u
banditflag8-9{*****}

```
```

Done! We got there thanks to [stackoverflow](https://stackoverflow.com/questions/12782827/how-to-find-the-particular-text-stored-in-the-file-data-txt-and-it-occurs-only).

### Level 10

Our final level together, for now, let’s `ls` this thing.

Another `data.txt` file, let’s `cat` it.

Ah heck, it was a trap! Use `clear` and we’ll go back to the [instructions](https://overthewire.org/wargames/bandit/bandit10.html):

*The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.*

Okay, so we need to search through the file and somehow use `=`… let’s give it a shot! Maybe we’ll try `grep` again from the earlier level.

```
<pre class="wp-block-code">```
$ grep data.txt -e =
Binary file data.txt matches

```
```

[StackExchange](https://unix.stackexchange.com/questions/335716/grep-returns-binary-file-standard-input-matches-when-trying-to-find-a-string) shows us that since the `data.txt` file starts with non-text, it treats it as binary and therefore won’t search it. Dam.

Let’s look at the other commands we can use.

There’s one called `strings`, let’s take a closer look with `strings --help`

If we use this commands and `|` pipe `grep` with a few `=` … we should be good to go, let’s try it!

```
<pre class="wp-block-code">```
$ strings data.txt | grep ===
========== the*2i"4
========== password
Z)========== is
&========== banditflag9-10{*****}

```
```

It’s not the prettiest method, it’s probably not the best way either, but it worked!

- - - - - -

Thanks for reading along with my bandit CTF journey! It’s been nice to have you.

If you have any feedback, please send me a message [@mrashleyball](https://twitter.com/mrashleyball).

This is Day 9 and 57 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [weekly newsletter](https://go.mrash.co/newsletter) to see the learning journey!

Happy Hacking.

## Bandit Level 10 – 14

Over The Wire’s Bandit is a Linux Capture The Flag that tests your hacking skills. In this video, we walk through Bandit levels 10 to 14. These are some of the more difficult levels, but our clear and concise explanations will help you get through them. By the end of this video, you’ll be one step closer to becoming a master hacker!

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/3ZJTmWjEevM?feature=oembed" title="Bandit Level 10 - 14 Walkthrough OverTheWire | Capture The Flag Guide | Bandit Levels 10 to 14 OTW" width="800"></iframe></div></figure>### Level 10

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/yAuQ15Zv/6edb4e4e-eacc-4eee-ab5a-5be7f7bbfb4e.jpg?source=viewer&v=20da1cacfa13520557781c8152b175a8](https://p146.p4.n0.cdn.getcloudapp.com/items/yAuQ15Zv/6edb4e4e-eacc-4eee-ab5a-5be7f7bbfb4e.jpg?source=viewer&v=20da1cacfa13520557781c8152b175a8)</figure>### Level 11

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/mXu2xl5e/583c80da-dd71-4ef6-88d6-24573c5ae3bf.jpg?source=viewer&v=7a69576de1987a003ee66114084f28b0](https://p146.p4.n0.cdn.getcloudapp.com/items/mXu2xl5e/583c80da-dd71-4ef6-88d6-24573c5ae3bf.jpg?source=viewer&v=7a69576de1987a003ee66114084f28b0)</figure>### Level 12

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/9ZugoZx2/2bb3513f-1cc0-4aa1-bfa1-64a5e0ee128a.jpg?source=viewer&v=c7bb69681b170cbc15a728877a7ead7c](https://p146.p4.n0.cdn.getcloudapp.com/items/9ZugoZx2/2bb3513f-1cc0-4aa1-bfa1-64a5e0ee128a.jpg?source=viewer&v=c7bb69681b170cbc15a728877a7ead7c)</figure>### Level 13

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/jkuWXbP2/f4038305-25df-4182-990d-3b43d4415f9b.jpg?source=viewer&v=9d434538fdbbf992ebefda992c503966](https://p146.p4.n0.cdn.getcloudapp.com/items/jkuWXbP2/f4038305-25df-4182-990d-3b43d4415f9b.jpg?source=viewer&v=9d434538fdbbf992ebefda992c503966)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOubX0PZ/73208d21-b059-4ea3-a40c-ff5c9c4eb1ee.jpg?source=viewer&v=808a68f66b5ab3aac7988e2ccd09ef93](https://p146.p4.n0.cdn.getcloudapp.com/items/nOubX0PZ/73208d21-b059-4ea3-a40c-ff5c9c4eb1ee.jpg?source=viewer&v=808a68f66b5ab3aac7988e2ccd09ef93)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZmQLE/53bbe757-d5a2-4df2-bc7d-947b409968c2.jpg?source=viewer&v=ff910508357e599592edc99327eea6c0](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZmQLE/53bbe757-d5a2-4df2-bc7d-947b409968c2.jpg?source=viewer&v=ff910508357e599592edc99327eea6c0)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/qGuxOeRl/68836624-f7d4-407e-9862-e89ad7a52249.jpg?source=viewer&v=2716be5268098d1fb58906abff3243b6](https://p146.p4.n0.cdn.getcloudapp.com/items/qGuxOeRl/68836624-f7d4-407e-9862-e89ad7a52249.jpg?source=viewer&v=2716be5268098d1fb58906abff3243b6)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/WnuD7jq1/b1626840-d5be-4a9b-a545-d10211b2a890.jpg?source=viewer&v=6b16b21d0bcd835e04c7240e8c8a102c](https://p146.p4.n0.cdn.getcloudapp.com/items/WnuD7jq1/b1626840-d5be-4a9b-a545-d10211b2a890.jpg?source=viewer&v=6b16b21d0bcd835e04c7240e8c8a102c)</figure>### Level 14

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/ApuDXpx5/99a60703-644a-48ea-908c-98f3321cb9da.jpg?source=viewer&v=d13803da5b731ab258ddaf020eb478da](https://p146.p4.n0.cdn.getcloudapp.com/items/ApuDXpx5/99a60703-644a-48ea-908c-98f3321cb9da.jpg?source=viewer&v=d13803da5b731ab258ddaf020eb478da)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQOwgp/d17b6e2e-4894-4d96-afe1-8f5adf098970.jpg?source=viewer&v=eb787c1b1ef2187cd4752ce850e0e6fe](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQOwgp/d17b6e2e-4894-4d96-afe1-8f5adf098970.jpg?source=viewer&v=eb787c1b1ef2187cd4752ce850e0e6fe)</figure>## Bandit 15 – 19

Welcome back to Over The Wire’s Bandit the Linux Capture The Flag that tests your hacking skills. Let’s walk through Bandit levels 15 to 19 which again increase in difficulty, but let me help you get through them. By the end of this video, you’ll be one step closer to becoming a master hacker… hopefully.

### Level 15

<figure class="wp-block-image" id="block-98aa5fa9-b4c8-4dce-b649-b2ff0b21d676">![https://p146.p4.n0.cdn.getcloudapp.com/items/kpuW8xgd/b2827242-a3fc-4501-b45e-db453bd8c7cf.jpeg?v=3202df0349376216f775e165fd77b863](https://p146.p4.n0.cdn.getcloudapp.com/items/kpuW8xgd/b2827242-a3fc-4501-b45e-db453bd8c7cf.jpeg?v=3202df0349376216f775e165fd77b863)</figure>### Level 16

<figure class="wp-block-image" id="block-3aa3585c-70c0-41b5-b46a-838e0a72fdb7">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXOjr/438a81fe-636b-4982-b857-08dc6783a083.jpeg?v=f0f8911e8e1b2d5db58e216c2d446e0b](https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXOjr/438a81fe-636b-4982-b857-08dc6783a083.jpeg?v=f0f8911e8e1b2d5db58e216c2d446e0b)</figure>### Level 17

<figure class="wp-block-image" id="block-e4ada861-4dd6-421b-b8fd-bcc85a8d85d1">![https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6rDg/1c7c5278-b3d2-4828-a947-64d990a68e1e.jpeg?v=026fa065376c2366b0772b36b8e3beb5](https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6rDg/1c7c5278-b3d2-4828-a947-64d990a68e1e.jpeg?v=026fa065376c2366b0772b36b8e3beb5)</figure><figure class="wp-block-image" id="block-a1c68592-0c07-41fd-bde4-38747a6a9c12">![https://p146.p4.n0.cdn.getcloudapp.com/items/5zuPrqQd/54053e97-2774-4eda-a952-2f3d2a98c2d8.jpeg?v=9b3aa6d7188363c2117a01a020a5d4d3](https://p146.p4.n0.cdn.getcloudapp.com/items/5zuPrqQd/54053e97-2774-4eda-a952-2f3d2a98c2d8.jpeg?v=9b3aa6d7188363c2117a01a020a5d4d3)</figure><figure class="wp-block-image" id="block-cc3ad4a5-04d5-4ee4-afc7-2a6e9cf3d749">![https://p146.p4.n0.cdn.getcloudapp.com/items/p9uQO9W6/a45ae076-accb-4afb-a5cc-f6158f63ce7e.jpeg?v=26d45f17279488efa7536f8891f1bac0](https://p146.p4.n0.cdn.getcloudapp.com/items/p9uQO9W6/a45ae076-accb-4afb-a5cc-f6158f63ce7e.jpeg?v=26d45f17279488efa7536f8891f1bac0)</figure><figure class="wp-block-image" id="block-e4874700-c7ef-43af-95aa-96b5d8fcdca9">![https://p146.p4.n0.cdn.getcloudapp.com/items/GGuzKjDy/015360ec-f78d-405c-aa41-4ee69d16bb96.jpeg?v=b8d613654c243c4ebe9fe1a0815108e8](https://p146.p4.n0.cdn.getcloudapp.com/items/GGuzKjDy/015360ec-f78d-405c-aa41-4ee69d16bb96.jpeg?v=b8d613654c243c4ebe9fe1a0815108e8)</figure><figure class="wp-block-image" id="block-382d594d-261a-4849-8104-7a6751ebdb6a">![https://p146.p4.n0.cdn.getcloudapp.com/items/YEuWkE7g/3e62dc25-ca74-4fc7-8110-3d504e3f586b.jpeg?v=8c929c831e13a14dc5eed47bbf2a7933](https://p146.p4.n0.cdn.getcloudapp.com/items/YEuWkE7g/3e62dc25-ca74-4fc7-8110-3d504e3f586b.jpeg?v=8c929c831e13a14dc5eed47bbf2a7933)</figure>### Level 18

<figure class="wp-block-image" id="block-ce32c38a-97ac-493d-910b-2956011eeb30">![https://p146.p4.n0.cdn.getcloudapp.com/items/P8u7QqJG/676cfb9f-7bd0-4978-bfab-1197a50b0364.jpeg?v=34a827188655ea3a8e84db1f4d93bd69](https://p146.p4.n0.cdn.getcloudapp.com/items/P8u7QqJG/676cfb9f-7bd0-4978-bfab-1197a50b0364.jpeg?v=34a827188655ea3a8e84db1f4d93bd69)</figure>### Level 19

<figure class="wp-block-image" id="block-91fe1a83-3ff2-4634-920b-b011141481ff">![https://p146.p4.n0.cdn.getcloudapp.com/items/8Lu10KvO/1d10b18d-cc73-40ec-ae74-0bf53c40bbed.jpeg?v=e373d90a2dbbfeb5da458730f3e765fc](https://p146.p4.n0.cdn.getcloudapp.com/items/8Lu10KvO/1d10b18d-cc73-40ec-ae74-0bf53c40bbed.jpeg?v=e373d90a2dbbfeb5da458730f3e765fc)</figure>## Bandit 20 – 24 (Coming Soon)

## Bandit 25 – 29

<figure class="wp-block-image size-large">![](https://p146.p4.n0.cdn.getcloudapp.com/items/DOurK8DW/0b16cc91-4b65-4053-9692-0a6ee07b635f.jpg?v=64b6e77dd10d0f9740e3fd26d75cebe8)</figure>### Level 25

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/04uWvKx6/449ec78c-ffb5-4320-adfa-59b58177928c.jpeg?v=4c510fc6c29104507794e7982d36b991](https://p146.p4.n0.cdn.getcloudapp.com/items/04uWvKx6/449ec78c-ffb5-4320-adfa-59b58177928c.jpeg?v=4c510fc6c29104507794e7982d36b991)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/bLu5ZmqL/fef4ccb4-1ec9-44f4-894b-6181748079ae.jpeg?v=19305edcdb4b0508d2e69ceedcc0a142](https://p146.p4.n0.cdn.getcloudapp.com/items/bLu5ZmqL/fef4ccb4-1ec9-44f4-894b-6181748079ae.jpeg?v=19305edcdb4b0508d2e69ceedcc0a142)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOubLN5E/1ebfd960-fed1-408b-bca9-b27774f8514a.jpeg?v=9f87140caff2f0dae154c332a7778abb](https://p146.p4.n0.cdn.getcloudapp.com/items/nOubLN5E/1ebfd960-fed1-408b-bca9-b27774f8514a.jpeg?v=9f87140caff2f0dae154c332a7778abb)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/6quGJBvQ/7b6f8fe1-64de-4f17-8a9b-3a9006de2bfb.jpeg?v=c8d089441561f36a60a215822c5ec67e](https://p146.p4.n0.cdn.getcloudapp.com/items/6quGJBvQ/7b6f8fe1-64de-4f17-8a9b-3a9006de2bfb.jpeg?v=c8d089441561f36a60a215822c5ec67e)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/jkuWRKEm/1c67a9f5-301f-43b3-add9-2557e9a284fa.jpeg?v=bf2bfe9ac3fd646e6d24d8ddfee797bd](https://p146.p4.n0.cdn.getcloudapp.com/items/jkuWRKEm/1c67a9f5-301f-43b3-add9-2557e9a284fa.jpeg?v=bf2bfe9ac3fd646e6d24d8ddfee797bd)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/mXu2GqPW/229a604a-30bf-4ce6-83bf-aad6e46ae28e.jpeg?v=2a30257ce00d42eb9ce99feec71a7baf](https://p146.p4.n0.cdn.getcloudapp.com/items/mXu2GqPW/229a604a-30bf-4ce6-83bf-aad6e46ae28e.jpeg?v=2a30257ce00d42eb9ce99feec71a7baf)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/X6uQ7zbP/9568ffbc-5db9-4fe7-b494-a5c4f3b485ae.jpeg?v=19d4e87858a6ac1fc13da43a6cf1692c](https://p146.p4.n0.cdn.getcloudapp.com/items/X6uQ7zbP/9568ffbc-5db9-4fe7-b494-a5c4f3b485ae.jpeg?v=19d4e87858a6ac1fc13da43a6cf1692c)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZJdEo/483ade43-9364-4c99-9478-736e017cb69d.jpeg?v=d311d4c17e492ed9bd3e0f18d98ebf12](https://p146.p4.n0.cdn.getcloudapp.com/items/RBuZJdEo/483ade43-9364-4c99-9478-736e017cb69d.jpeg?v=d311d4c17e492ed9bd3e0f18d98ebf12)</figure>### Level 26

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/8Lu1YJpy/80619a0c-624c-476a-b059-410936a60bbf.jpeg?v=9ec468cf925adf6cf9f57eacb475256b](https://p146.p4.n0.cdn.getcloudapp.com/items/8Lu1YJpy/80619a0c-624c-476a-b059-410936a60bbf.jpeg?v=9ec468cf925adf6cf9f57eacb475256b)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/L1u9vgWD/52505c45-f6d9-43ce-a418-f6d59a40993e.jpeg?v=f9c3ea5a3627a7a6b93124649e61c234](https://p146.p4.n0.cdn.getcloudapp.com/items/L1u9vgWD/52505c45-f6d9-43ce-a418-f6d59a40993e.jpeg?v=f9c3ea5a3627a7a6b93124649e61c234)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/GGuz5NEm/d60db122-55ed-4ebb-95b9-bd6781cd9f31.jpeg?v=70df9fad8bacab171a9b001ef93ecdd9](https://p146.p4.n0.cdn.getcloudapp.com/items/GGuz5NEm/d60db122-55ed-4ebb-95b9-bd6781cd9f31.jpeg?v=70df9fad8bacab171a9b001ef93ecdd9)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Qwudw7LD/bae05f32-4762-4b8f-afbc-b566dce6fe60.jpeg?v=6da418d11d17031e73b8e9f7ad294491](https://p146.p4.n0.cdn.getcloudapp.com/items/Qwudw7LD/bae05f32-4762-4b8f-afbc-b566dce6fe60.jpeg?v=6da418d11d17031e73b8e9f7ad294491)</figure><figure class="wp-block-image">![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/318df1e6-0c5e-48e4-b216-2bd97d66d547/Untitled.png)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/WnuD6NDZ/55d37cc9-5c88-4ade-ad1e-f27a15e549cb.jpeg?v=ca0c83ade5288e6ec8a73b9f66ee407c](https://p146.p4.n0.cdn.getcloudapp.com/items/WnuD6NDZ/55d37cc9-5c88-4ade-ad1e-f27a15e549cb.jpeg?v=ca0c83ade5288e6ec8a73b9f66ee407c)</figure>### Level 27

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/E0uZLqZp/de30ed72-4de6-4661-b277-f42a382dfdc9.jpeg?v=1af7a808dcbcd417fc7542c7e23a2db3](https://p146.p4.n0.cdn.getcloudapp.com/items/E0uZLqZp/de30ed72-4de6-4661-b277-f42a382dfdc9.jpeg?v=1af7a808dcbcd417fc7542c7e23a2db3)</figure>### Level 28

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/qGux6oZy/77cf69db-b88a-43bc-9437-c1d906889d54.jpeg?v=47d3fdf5d1d698f4426ae79f3c28b14c](https://p146.p4.n0.cdn.getcloudapp.com/items/qGux6oZy/77cf69db-b88a-43bc-9437-c1d906889d54.jpeg?v=47d3fdf5d1d698f4426ae79f3c28b14c)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQWrE4/69c7d052-1947-440e-8e0f-81c953fefc65.jpeg?v=3d97491ff17f8be42ee3561432018515](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uQWrE4/69c7d052-1947-440e-8e0f-81c953fefc65.jpeg?v=3d97491ff17f8be42ee3561432018515)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/OAujlr2G/921a91d5-c8ef-4f5b-a279-7c2a8e9a2d6a.jpeg?v=0af1074c8932d902ed1881aee6f5db67](https://p146.p4.n0.cdn.getcloudapp.com/items/OAujlr2G/921a91d5-c8ef-4f5b-a279-7c2a8e9a2d6a.jpeg?v=0af1074c8932d902ed1881aee6f5db67)</figure>### Level 29

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Jru8eWyJ/c639eb64-c84f-42f6-9588-306d4959b7af.jpeg?v=86d0eb8250c907b1067007675a923801](https://p146.p4.n0.cdn.getcloudapp.com/items/Jru8eWyJ/c639eb64-c84f-42f6-9588-306d4959b7af.jpeg?v=86d0eb8250c907b1067007675a923801)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/6quGJBNd/c0c4c215-1225-41e4-813c-3edb51eafa03.jpeg?v=f2aa0348ab48408ef9cb2e3fa3ba8c90](https://p146.p4.n0.cdn.getcloudapp.com/items/6quGJBNd/c0c4c215-1225-41e4-813c-3edb51eafa03.jpeg?v=f2aa0348ab48408ef9cb2e3fa3ba8c90)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/qGux6oqy/c13c923d-70be-4aa4-91ab-2cfac802fe92.jpeg?v=3313ff5c981df5bf12b9d3fd70e81b2f](https://p146.p4.n0.cdn.getcloudapp.com/items/qGux6oqy/c13c923d-70be-4aa4-91ab-2cfac802fe92.jpeg?v=3313ff5c981df5bf12b9d3fd70e81b2f)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/P8u7XR2y/fe151a61-32ab-4a91-9881-764683cbad62.jpeg?v=a6bc2b27b3f0b30d1b0ca3559803ef55](https://p146.p4.n0.cdn.getcloudapp.com/items/P8u7XR2y/fe151a61-32ab-4a91-9881-764683cbad62.jpeg?v=a6bc2b27b3f0b30d1b0ca3559803ef55)</figure>