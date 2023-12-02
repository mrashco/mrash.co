---
id: 5772
title: Automate The Boring Stuff With Python Practice Projects
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5772
url: "/?p=5772"
---

[Automate The Boring Stuff With Python](https://automatetheboringstuff.com/) is an incredible book, and course by [Al Sweigart](https://alsweigart.com/) to learn Python coding and computer science for the everyday person. With its straightforward learning approach, and succinct program examples and explanations, it’s many hobbyists’ go-to book for Python.

This article breaks down my personal solutions to the practice projects outlined at the end of most chapters. As I continue to learn Python and generally computer science, I enjoy seeing how others solve coding problems.

All practice projects can be found via this [GitHub Repo](https://github.com/mrashleyball/automate), feel free to clone it and/or use it however you like, note, please read the disclaimer before doing so below. Also see the cloned [Replit](https://replit.com/@mrashleyball/automate), to use the programs use the Console with the command format of `python folder/file.py`.

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/automate?lite=true" width="100%"></iframe>*Disclaimer, this is for version 2 of the book, code is written of my own doing, any assistance will be mentioned or linked. Highly recommended you solve practice projects yourself before seeing other’s code, don’t rob yourself of any learning opportunities. I do not claim to be a professional, please share any suggestions or feedback to improve my code or this article.*

## [Lists](https://automatetheboringstuff.com/2e/chapter4/)

### Comma Code

The first practice project comes in chapter 4 which involves taking a list and printing out the items as a new string. This can be solved using two variables, a `for loop` and indexing. The tricky part is solving how to print the items but to do something different on the last item.

The program takes the list, loops through it and adds each item to a string.

To define a `for loop` up until but not including the last item in the list, you can use a negative index `[:-1]`. This way each item can be added to the new string as intended, but the last item can be added with the `'and '`.

Note, that I’ve used format (f) strings in my example below.

<script src="https://gist.github.com/mrashleyball/b6ff631b2f87fc892c9ba476a5964657.js"></script>### Coin Flip Streaks

Alright, next up is finding streaks within random coin tosses, this was a bit of a tricky practice project, but a really good one. To map out the program, I used pseudo code, this helped me get a better idea of the steps involved. Simply, the program will toss a coin a certain number of times, store each toss as an item in a list, and then loop through the items to find a streak.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>I broke this program into two functions, 1) flip, and 2) streak. This keeps things organised, makes coding easier and abstracts away elements within the program.

So, the flip function is solely responsible for taking a number from the user, flipping the coin based on that number and storing the results in a list.

Then, the streak function takes that list to find the streaks, this was the most difficult part of the practice project. I found [this Reddit](https://www.reddit.com/r/learnpython/comments/6m8o4d/if_i_have_a_list_of_numbers_how_do_i_get_the/) post via r/learnpython which made things more simple for me. The problem was tracking if a streak was found or not, since we can use a `for loop` we know the current item. With that and indexing, we can figure out if we have a streak.

So, inside a `for loop`, using an `if` condition to match the current item to the last if that matches then a streak counter increases. This way, every item must be the same as the last to count up, once that counts up to a certain number, in this case, six, then we have a streak.

A separate variable called streaks increases and that is the final output that feeds back to the user.

<script src="https://gist.github.com/mrashleyball/8ccdcb23b073046033d51b160d7b5604.js"></script>### Character Picture Grid

This practice project took a lot of internal visual imagery to work for me, it reinforced the `for loop` which was great. As per the hints, you can use a `for loop` inside a `for loop` it feels a bit inception-like at first.

What helped me, was referring back to the list stored within grid, the first `for loop` is iterating over each list of items, and the second is iterating over each item within the lists. I know, it’s a bit confusing, but the more you go over it, the more it makes sense.

To help break this down further, I used the names rows and columns instead of the x and y axis, that just helped me. The draw function starts with declaring these variables and stores integer values, these match the item I want to first print out.

Within the second `for loop` we want to print out using indexing, this way we can print exactly the item we want.

Since we’re starting out in row position 8, and column position 0, meaning the first column and the last row item. Then we go up row by row within the second `for loop`, then column by column within the first `for loop`. Once the program reaches column 5, then it breaks out of the loop, and the character picture grid has been rotated and printed out to the terminal.

<script src="https://gist.github.com/mrashleyball/7619cc17096a3acf8c77636fa1c5f758.js"></script>## Dictionaries and Structuring Data

(Coming Soon)

This is day 50 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking/coding/learning.