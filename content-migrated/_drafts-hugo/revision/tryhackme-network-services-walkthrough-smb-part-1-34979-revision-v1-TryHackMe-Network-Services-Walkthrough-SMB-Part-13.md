---
id: 5380
title: TryHackMe Network Services Walkthrough SMB Part 1/3
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5380
url: "/?p=5380"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/DwPuDptnc2w?feature=oembed" title="TryHackMe Network Services 1 Part 1 SMB • Walkthrough" width="800"></iframe></div></figure>## Task 1 Get Connected

Questions

- Ready? Let’s get going! – No answer needed, carry on.

<div class="elementor elementor-5269" data-elementor-id="5269" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-650fe30 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="650fe30" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-19d1b1d" data-element_type="column" data-id="19d1b1d"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-75001c1 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="75001c1" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-2d39fa8" data-element_type="column" data-id="2d39fa8" data-settings="{"background_background":"gradient"}"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-background-overlay"></div><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-87a745b elementor-position-right elementor-vertical-align-middle elementor-view-default elementor-mobile-position-top elementor-widget elementor-widget-icon-box" data-element_type="widget" data-id="87a745b" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="icon-box.default"><div class="elementor-widget-container"><div class="elementor-icon-box-wrapper"><div class="elementor-icon-box-icon"> <span class="elementor-icon elementor-animation-">  </span> </div><div class="elementor-icon-box-content"> <span> **Free Checklist:** Hacker's Learning Path </span>

 Offline checklist to track your learning path, become a great hacker and stay on task.

 </div> </div> </div> </div><div class="elementor-element elementor-element-96a5f87 elementor-tablet-button-align-stretch elementor-button-align-stretch elementor-widget elementor-widget-form" data-element_type="widget" data-id="96a5f87" data-settings="{"button_width":"25","step_next_label":"Next","step_previous_label":"Previous","step_type":"number_text","step_icon_shape":"circle","ekit_we_effect_on":"none"}" data-widget_type="form.default"><div class="elementor-widget-container"> <form class="elementor-form" method="post" name="CTA - Hackers Checklist"> <input name="post_id" type="hidden" value="5269"></input> <input name="form_id" type="hidden" value="96a5f87"></input> <input name="referer_title" type="hidden" value=""></input><div class="elementor-form-fields-wrapper elementor-labels-"><div class="elementor-field-type-email elementor-field-group elementor-column elementor-field-group-email elementor-col-75 elementor-md-80 elementor-field-required"> <label class="elementor-field-label elementor-screen-only" for="form-field-email"> Email </label> <input aria-required="true" class="elementor-field elementor-size-xs  elementor-field-textual" id="form-field-email" name="form_fields[email]" placeholder="Enter Email Here" required="required" size="1" type="email"></input> </div><div class="elementor-field-group elementor-column elementor-field-type-submit elementor-col-25 e-form__buttons"> <button class="elementor-button elementor-size-xs" type="submit"> <span> <span class=" elementor-button-icon"> </span> <span class="elementor-button-text">Get</span> </span> </button> </div> </div> </form> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </section> </div> </div>## Task 2 Understanding SMB

- What does SMB stand for? – Server Message Block
- What type of protocol is SMB? – response-request
- What do clients connect to servers using? – TCP/IP
- What systems does Samba run on? – Unix

## Task 3 Enumerating SMB

Run nmap scan.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxEr8/495d025a-7b15-4222-a6e3-262081ec8fde.jpeg?v=bb76d881e7362c340426d2e881165c95](https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxEr8/495d025a-7b15-4222-a6e3-262081ec8fde.jpeg?v=bb76d881e7362c340426d2e881165c95)</figure>Run enum4linux scan.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/04uEgZ65/94fdb523-85de-4da8-9826-ee0c0ea16a59.jpeg?v=4b3296ecd8899cd8c492ce3c7b780b86](https://p146.p4.n0.cdn.getcloudapp.com/items/04uEgZ65/94fdb523-85de-4da8-9826-ee0c0ea16a59.jpeg?v=4b3296ecd8899cd8c492ce3c7b780b86)</figure>Questions:

- Conduct an nmap scan of your choosing, How many ports are open? – 3
- What ports is SMB running on? – 139/445
- Let’s get started with Enum4Linux, conduct a full basic enumeration. For starters, what is the workgroup name? – WORKGROUP
- What comes up as the name of the machine? – POLOSMB
- What operating system version is running? – 6.1
- What share sticks out as something we might want to investigate? – profiles

## Task 4 Exploiting SMB

Connect using `smbclient`:

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRmOLm/20eec8de-89e3-46f2-80dc-3b6d27a502dd.jpeg?v=c5caa032c750d46dee0f6cfce1bf3eef](https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRmOLm/20eec8de-89e3-46f2-80dc-3b6d27a502dd.jpeg?v=c5caa032c750d46dee0f6cfce1bf3eef)</figure>Use the `more` command, don’t forget the quotations!

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/lluE4lXW/070fe98c-60c8-4ad7-8bef-7a67e5216491.jpeg?v=9f8f1ed689e003f3350774456a5015a0](https://p146.p4.n0.cdn.getcloudapp.com/items/lluE4lXW/070fe98c-60c8-4ad7-8bef-7a67e5216491.jpeg?v=9f8f1ed689e003f3350774456a5015a0)</figure>Use `get` to copy the `id_rsa` file from the server to your machine:

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxERj/9a8b619c-e617-48f4-a2c5-8036f4685d7e.jpeg?v=852578264d21f58d80460ee97014e6ed](https://p146.p4.n0.cdn.getcloudapp.com/items/4guKxERj/9a8b619c-e617-48f4-a2c5-8036f4685d7e.jpeg?v=852578264d21f58d80460ee97014e6ed)</figure>Questions:

- What would be the correct syntax to access an SMB share called “secret” as user “suit” on a machine with the IP 10.10.10.2 on the default port? – smbclient [//10.10.10.2/secret](//10.10.10.2/secret) -U suit -p 445
- Great! Now you’ve got a hang of the syntax, let’s have a go at trying to exploit this vulnerability. You have a list of users, the name of the share (smb) and a suspected vulnerability. – No answer needed.
- Does the share allow anonymous access? Y/N? – Y
- Great! Have a look around for any interesting documents that could contain valuable information. Who can we assume this profile folder belongs to? – John Cactus
- What service has been configured to allow him to work from home? – ssh
- Okay! Now we know this, what directory on the share should we look in? – .ssh
- This directory contains authentication keys that allow a user to authenticate themselves on, and then access, a server. Which of these keys is most useful to us? – id\_rsa
- What is the smb.txt flag? – THM{\*\*\*\*\*\*\*\*\*\*\*}

This is Day 40 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, follow the [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.