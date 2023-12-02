---
id: 5377
title: "Cowsays What CTF \u2022 A Beginner Linux Project"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5377
url: "/?p=5377"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Want a beginner Linux CTF (Capture The Flag)? **Moo**ve over, here’s Cowsays What CTF. A simple question-based python program to test your beginner Linux level skills.

This simple CTF will use Linux commands to install a program, execute it and interact with it. Cowsays What CTF is inspired by [TryHackMe](https://tryhackme.com/) and [OverTheWire’s Bandit](https://overthewire.org/wargames/bandit/).

*Disclaimer, if you need help getting started with Linux, see [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/).*

## Getting Started

Before you tackle the challenge, understand the scope, here’s what you need to know:

- **Challenge**: 14 levels, 1 question per level, each question requires an answer.
- **Players:** 1 (singleplayer).
- **Difficulty:** Easy – new to Linux.
- **Environment**: local Debian-based Linux installation e.g. [Ubunutu in VirtualBox](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/).
- **Commands**: `ls`, `sudo`, `cp`, `man`.
- **Help**: External research, in-game hints and walkthrough below.

To start, click the play button below, if there’s an issue, use the [direct link](https://replit.com/@mrashleyball/cowsayswhatctf) ([](https://replit.com/@mrashleyball/cowsayswhatctf)<https://replit.com/@mrashleyball/cowsayswhatctf>):

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/cowsayswhatctf?embed=true" width="100%"></iframe><div class="elementor elementor-5199" data-elementor-id="5199" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-f35065f elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="f35065f" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-7a7d957" data-element_type="column" data-id="7a7d957"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-ca68749 overwrite elementor-widget elementor-widget-elementskit-tab" data-element_type="widget" data-id="ca68749" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-tab.default"><div class="elementor-widget-container"><div class="ekit-wid-con"><div class="elementkit-tab-wraper   elementskit-fitcontent-tab ">- [ <span aria-hidden="true" class="fas fa-hat-cowboy-side elementskit-tab-icon"></span><div class="ekit-tab-title-group"> <span class="elementskit-tab-title">CowsaysWhatCTF</span> </div> ](content-4509f2d6353d247ec932)
- [<div class="ekit-tab-title-group"> <span class="elementskit-tab-title">More Coming Soon</span> </div> ](content-35d76b76353d247ec932)
 
<div class="tab-content elementkit-tab-content"><div aria-labelledby="content-4509f2d6353d247ec932-tab" class="tab-pane elementkit-tab-pane elementor-repeater-item-4509f2d  active show" id="content-4509f2d6353d247ec932" role="tabpanel"><div class="animated fadeIn"><div class="widgetarea_warper widgetarea_warper_editable" data-elementskit-widgetarea-index="1" data-elementskit-widgetarea-key="ca68749"><div class="widgetarea_warper_edit" data-elementskit-widgetarea-index="1" data-elementskit-widgetarea-key="ca68749">  <span class="elementor-screen-only">Edit</span> </div><div class="elementor-widget-container"><div class="elementor elementor-5200" data-elementor-id="5200" data-elementor-type="wp-post"><div class="elementor-inner"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-a5538c4 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="a5538c4" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-55b9a2c" data-element_type="column" data-id="55b9a2c"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-c2de485 elementor-widget elementor-widget-eael-protected-content" data-element_type="widget" data-id="c2de485" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="eael-protected-content.default"><div class="elementor-widget-container"><div class="eael-protected-content-message"> </div><div class="eael-password-protected-content-fields"> <form id="eael_protected_content_form_c2de485" method="post" name="eael_protected_content_form_c2de485"> <input class="eael-password" name="protection_password_c2de485" placeholder="Enter flag{******************************}" type="password"></input> <input name="eael_protected_content_nonce_c2de485" type="hidden" value="cb8e0e9723"></input> <input class="eael-submit" type="submit" value="Submit"></input> </form> </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </div> </div><div aria-labelledby="content-35d76b76353d247ec932-tab" class="tab-pane elementkit-tab-pane elementor-repeater-item-35d76b7 " id="content-35d76b76353d247ec932" role="tabpanel"><div class="animated fadeIn"><div class="widgetarea_warper widgetarea_warper_editable" data-elementskit-widgetarea-index="2" data-elementskit-widgetarea-key="ca68749"><div class="widgetarea_warper_edit" data-elementskit-widgetarea-index="2" data-elementskit-widgetarea-key="ca68749">  <span class="elementor-screen-only">Edit</span> </div><div class="elementor-widget-container"><div class="elementor elementor-5214" data-elementor-id="5214" data-elementor-type="wp-post"><div class="elementor-inner"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-9ec2683 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="9ec2683" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-4eec427" data-element_type="column" data-id="4eec427"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-97f64f2 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="97f64f2" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">More CTFs in the works!

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>Enjoy the Cowsays What CTF challenge. If you need a bit more help, here’s what you need to do to play:

1. Setup Linux however you like e.g. [Ubuntu using VirtualBox](https://mrash.co/how-to-setup-ubuntu-using-virtualbox/) or [Kali via WSL](https://mrash.co/kali-linux-wsl-without-microsoft-store/).
2. Use the [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/) and open the terminal to start.
3. Begin the Cowsays What CTF above by pressing the play button.
4. If you’re stuck, see the Writeup below – spoiler warning.

## About The Project

This is a fun side-project to practice basic Linux commands for users while also having an excuse to practice python, it’s a win-win project. If you’d like more detail, see Reflection below.

- What is Cowsays What CTF? A simple python program running in a Replit terminal so it can be embedded and shared.
- What’s a CTF? Capture The Flags are fun ways to learn tech skills in Cyber Security.
- Is Cowsays What CTF *really* a CTF? Kind of, there are many different types of CTFs.
- Why does Cowsays What CTF exist? For fun! It’s fun to learn, so both for the user and author (me)!
- Who is Cowsays What CTF for? Anyone new to learning Linux commands and basic terminal interactions.

<div class="elementor elementor-5269" data-elementor-id="5269" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-650fe30 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="650fe30" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-19d1b1d" data-element_type="column" data-id="19d1b1d"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-75001c1 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="75001c1" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-2d39fa8" data-element_type="column" data-id="2d39fa8" data-settings="{"background_background":"gradient"}"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-background-overlay"></div><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-87a745b elementor-position-right elementor-vertical-align-middle elementor-view-default elementor-mobile-position-top elementor-widget elementor-widget-icon-box" data-element_type="widget" data-id="87a745b" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="icon-box.default"><div class="elementor-widget-container"><div class="elementor-icon-box-wrapper"><div class="elementor-icon-box-icon"> <span class="elementor-icon elementor-animation-">  </span> </div><div class="elementor-icon-box-content"> <span> **Free Checklist:** Hacker's Learning Path </span>

 Offline checklist to track your learning path, become a great hacker and stay on task.

 </div> </div> </div> </div><div class="elementor-element elementor-element-96a5f87 elementor-tablet-button-align-stretch elementor-button-align-stretch elementor-widget elementor-widget-form" data-element_type="widget" data-id="96a5f87" data-settings="{"button_width":"25","step_next_label":"Next","step_previous_label":"Previous","step_type":"number_text","step_icon_shape":"circle","ekit_we_effect_on":"none"}" data-widget_type="form.default"><div class="elementor-widget-container"> <form class="elementor-form" method="post" name="CTA - Hackers Checklist"> <input name="post_id" type="hidden" value="5269"></input> <input name="form_id" type="hidden" value="96a5f87"></input> <input name="referer_title" type="hidden" value=""></input><div class="elementor-form-fields-wrapper elementor-labels-"><div class="elementor-field-type-email elementor-field-group elementor-column elementor-field-group-email elementor-col-75 elementor-md-80 elementor-field-required"> <label class="elementor-field-label elementor-screen-only" for="form-field-email"> Email </label> <input aria-required="true" class="elementor-field elementor-size-xs  elementor-field-textual" id="form-field-email" name="form_fields[email]" placeholder="Enter Email Here" required="required" size="1" type="email"></input> </div><div class="elementor-field-group elementor-column elementor-field-type-submit elementor-col-25 e-form__buttons"> <button class="elementor-button elementor-size-xs" type="submit"> <span> <span class=" elementor-button-icon"> </span> <span class="elementor-button-text">Get</span> </span> </button> </div> </div> </form> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </section> </div> </div>## About The Program

Let’s break down the Cowsays What CTF program, a simple python program. It’s hosted via GitHub and distributed via Replit.

Here’s the pseudo-code:

```
<pre class="wp-block-code">```
#1 Welcome message, with instructions
#2 Control menu???
#3 Define help menu + Define hint menu
#4 Define answers
#5 Display questions(1-15), display expected input
#6 Auth user input

```
```

The goal was to use variables to not have so much duplicate code, it’s still a work in progress, any feedback is welcome. Here’s the welcome message and main variables:

```
<pre class="wp-block-code">```
cq = '[Research] What Linux program can make a cow say something?' # Current Question

print('''Welcome to Cowsays What CTF!! 
You'll have 14 questions to complete, use google, a Debian based Linux distro and a bash CLI.
Use 'help' to see the question again, and use 'hint' if you're stuck on the question.
Question 0: ''' + cq)

ui = ' ' # User Input
qc = 0 # Question Counter
hc = 0 # Hint Counter
h = ' '
a = ' ' # Answer

```
```

Here’s the main game loop and the hint and help menu.

```
<pre class="wp-block-code">```
# Help + Hint Menu
if ui == 'help' or ui == 'Help':
	print('[Help] You\\'re up to Question ' + str(qc) + ': ' + cq)
elif ui == 'hint' or ui == 'Hint':
	print('[Hint] ' + h + ' [Characters] ' + str((len(a))))

```
```

And here’s an example of the first question:

```
<pre class="wp-block-code">```
if qc == 0:
	a = 'cowsay'
	h = 'cowsay what?'
	ui = input('Answer Q' + str(qc) + ': ')
	if ui == a:
		print('[Answer] ' + a + ' - Good work!')
		qc +=1
		cq = 'How do you install the program?'
		print('Q' + str(qc) + ': ' + cq)

```
```

If you have feedback or any suggestions, feel free to reach out or fork via GitHub. If you’d like to learn Python, feel free to check out [Intro To Python • Free Python Starter Guide](https://mrash.co/intro-to-python-free-python-starter-guide/) and the various Python projects like [Is It Raining?](https://mrash.co/python-basic-project-idea-is-it-raining/), [Mad Lib Game](https://mrash.co/mad-lib-game-beginner-python-project/), [Username Generator](https://mrash.co/username-generator-beginner-python-program/), [Random Number Generator](https://mrash.co/random-number-generator-easy-python-project/), [Bagels](https://mrash.co/bagels-beginner-python-project/), and [ZigZag](https://mrash.co/zigzag-beginner-python-project/).

## Cowsays What CTF Writeup

Okay, warning, spoilers ahead.

1. \[Research\] What Linux program can make a **cow say** something?
    - \[Hint\] cowsay what?
    - \[Answer\] `cowsay`
2. How do you install the program?
    - \[H\] Debiasn-based systems: `sudo <package manager> install <program>`
    - \[A\] `sudo apt install cowsay`
3. How do you execute (or run) the program?
    - \[H\] Type `<program>` and a message, use CTRL + C if needed. You may need to use /usr/games/&lt;program&gt;…
    - \[A\] `cowsay`
4. What other program was installed?
    - \[H\] List `/usr/games` – don’t say, think.
    - \[A\] `cowthink`
5. How do you access the **man**ual page for this program?
    - \[H\] **man** I wonder how…
    - \[A\] `man cowsay`
6. How do you make the cow moo?
    - \[H\] `<program> <argument>`
    - \[A\] `cowsay moo`
7. Using the man page, how do you have the cow moo and appear **dead**?
    - \[H\] Read the man page and use the `-` before a letter e.g. `cowsay -h`
    - \[A\] `cowsay -d moo`
8. Using the same format, how do you make the cow moo and appear **paranoid**?
    - \[H\] Use the same format as you just did `cowsay -<letter> moo`
    - \[A\] `cowsay -p moo`
9. Using the same format, how do you make the cow moo and appear **greedy**?
    - \[H\] Use the same format as you just did `cowsay -<letter> moo`
    - \[A\] `cowsay -g moo`
10. How do you display a list of other cows (if you can call them cows)?
    - \[H\] man, if only there was a help page!
    - \[A\] `cowsay -l`
11. How do you make a **dragon** say **raw**?
    - \[H\] man, if only there was a help page!
    - \[A\] `cowsay -f dragon raw`
12. How do you make a **turtle** say **hello**?
    - \[H\] man, if only there was a help page!
    - \[A\] `cowsay -f turtle hello`
13. How do you make the cow wink it’s right eye and say moo?
    - \[H\] Use the `-` symbol and a captial `O` for the eyes string – there’s a switch you need.
    - \[A\] `cowsay -e -O moo`
14. \[Research\] How do you make the cow’s tounge look like this `()` and say moo?
    - \[H\] Hm, this is wiki hard.
    - \[A\] `cowsay -T \\(\\) moo`

## Reflection

Cowsays What CTF has been a fun mini project to think up and publish, I’ve really enjoyed it. I’m also learning Linux and Python, so I’m always looking for fun projects to practice at my current skill level.

I love teaching IT, so I can’t help but focus on projects that help others learn. Building a python program about learning Linux is a good way to learn python and Linux, it’s a circle.

I’m also fascinated with CTFs, I grew up playing video games so learning CyberSec in a gamified format is a no-brainer. Recently I read [DarkStar’s Making The Mountain](https://tryhackme.com/resources/blog/making-the-mountain) \[[video](https://youtu.be/qQ6jQV7kzcw)\] which really opened my eyes to the world of constructing Cyber Security training.

I guess this is something I really want to do more of and this is my first step toward it! I hope you enjoy it. Thanks and helpful links [Wiki – cowsay](https://en.wikipedia.org/wiki/Cowsay), [Have a cow at the Linux command line](https://opensource.com/article/18/12/linux-toy-cowsay), and [Linux Unhatched Course Notes](https://mrash.co/linux-unhatched-cisco-course-review-and-notes/).

This is Day 43 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/) , subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the [CyberSec](https://mrash.co/starting-out-in-cyber-security/) journey! If you like, follow the [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.