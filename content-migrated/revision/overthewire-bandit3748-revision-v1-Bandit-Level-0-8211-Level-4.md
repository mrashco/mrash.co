---
id: 5844
title: Bandit Level 0 &#8211; Level 4
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5844
url: "/?p=5844"
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

## Level 0

Okay, let’s get started with Bandit Level 0 and connect to the game via Secure Socket Shell (SSH).

This tells Linux to run the `ssh` command, connect to `bandit.labs.overthewire.org` via port `2220` and user `bandit0`. So all together it looks like `ssh bandit0@bandit.labs.overthewire.org -p 2220`.

Then, type `yes` and hit `enter` to complete the connection.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXg7g/dec86188-5f56-427a-b6d9-ee1464f7c2d9.jpeg?v=1c7e58bc8f158f35f19a88e1158ba2b4](https://p146.p4.n0.cdn.getcloudapp.com/items/nOubXg7g/dec86188-5f56-427a-b6d9-ee1464f7c2d9.jpeg?v=1c7e58bc8f158f35f19a88e1158ba2b4)</figure>Take a moment to read the rules and check out the welcome message.

## Level 1

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

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>## Level 2

Alrighty, now it’s getting serious with Bandit Level 2. First things first, let’s read that goal. *The password for the next level is stored in a **file** called **–** located in the home directory*

Okay, seems easy, same as last round, `ls` then `cat`…right?

Try it, but you’ll see the issue. We need to specify the exact file path in order for Linux to understand. We’ll add `./` which tells Linux “hey, I’m in this folder”.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6JrN/0b40a03c-844c-4a1a-9529-6378b9d1678b.jpeg?v=6726588a209f627ca2a96dc218d1e0d7](https://p146.p4.n0.cdn.getcloudapp.com/items/7Kuk6JrN/0b40a03c-844c-4a1a-9529-6378b9d1678b.jpeg?v=6726588a209f627ca2a96dc218d1e0d7)</figure>That looks pretty good, so let’s follow the same process of `exit` &gt; `up` &gt; change user, in this case, `bandit2` &gt; and paste the flag as the password.

## Level 3

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

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>## Level 4

Let’s go beyond `ls` and `cat` and start changing the directory (aka folders).

So what’s the goal? *The password for the next level is stored in a hidden file in the **inhere** directory.*

Okay, our clue is the directory is hidden, tuck that away for now. Let’s view what’s around and move into our directory using `cd`. You might notice I’m using `&&` to chain commands together, a neat little trick I’ve picked up. So try `cd inhere && ls` and we should see our file but it’s hidden.

We need to introduce flags, these are like switches we can use to add features to our programs.

`ls` displays files, but if we turn on `-a` it will also display hidden files. Let’s try it!

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Kou1jmbQ/616bf51e-7a5c-499d-9993-14d139643342.jpeg?v=4507daf489634fb74c775d9728a648e7](https://p146.p4.n0.cdn.getcloudapp.com/items/Kou1jmbQ/616bf51e-7a5c-499d-9993-14d139643342.jpeg?v=4507daf489634fb74c775d9728a648e7)</figure>Nice! We got the flag for Bandit Level 4, nice. Now let’s exit and move on to the next level in [Bandit Levels 5 to 9](https://mrash.co/bandit-level-5-level-9/).

Thanks for reading and I hope you learned something from this little exercise. This is days 4 and 56 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.