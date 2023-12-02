---
title: CS50P Problem Set Guide
author: Mr Ash
type: "post"
published: 2022-07-17
lastUpdated: 2022-11-05
url: "/cs50-python-problem-set-guide/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/ApuJqjpQ/00d66ae7-9d96-44e0-9459-3fc3f4fae991.jpeg?v=60d7c8ba4915850993c1d0f2bdf76cf4
categories: Programming
tags:
    - CS50P
    - Python
---

Hello, world and welcome, this is a breakdown, or guide, to the problem sets (psets) to [CS50’s Introduction to Programming with Python (CS50P)](https://cs50.harvard.edu/python/).

If you’re unaware, CS50 Python comes from Havard which operates edx CS50. It’s a great introduction to the programming language Python. If you’re brand new to Computer Science (CS) or have a background in technology, CS50 covers the fundamentals really well. It’s one of the best places to learn Python online.

For me learning Cyber Security, I’m fascinated with the abilities programming unlocks like automation and threat detection. However, I’ve found learning any programming language really difficult. So, I write and share articles like this to help myself reinforce what I learn while (hopefully) distilling some help your way.

*Disclaimer, following CS50’s [Academic Honesty](https://cs50.harvard.edu/python/2022/honesty/), this article will be written as if you’ve asked for help and therefore will not show my code. However, I will share thoughts and Python constructs that helped me solve each one. PS, big shoutout to the CS50 community on Discord for their help, lots of amazing people there. PSS, I’m a fellow student, I’m not a professional nor do I claim my code is of any standard, code your way.*

## Functions, Variables

Most of the starting psets involve functions such as `input()`, `print()` and a single variable.

Let’s take a look at Week 0:

**[Indoor Voice](https://cs50.harvard.edu/python/2022/psets/0/indoor/):** this can be completed in 3 lines of code using string methods and a single variable.

**[Playback Speed](https://cs50.harvard.edu/python/2022/psets/0/playback/):** similar to `indoor` with 3 lines of code, but using a different string method. I used `str.replace()` to complete this problem set.

**[Making Faces](https://cs50.harvard.edu/python/2022/psets/0/faces/):** the same length of code again, and also the same string method can be used. If stuck, you can copy/paste emojis into your code editor.

**[Einstein](https://cs50.harvard.edu/python/2022/psets/0/einstein/)**: a few more lines might be needed for this pset, here’s my pseudo code `# E = mc2, mass + c (speed of light 300000000) squared`. You’ll need to convert the user’s input to an int and use some math operators to get the end result.

**[Tip Calculator](https://cs50.harvard.edu/python/2022/psets/0/tip/)**: this one escalates quickly imo, well for me anyway. I completed this pset within 20 lines of code, and multiple variables and defined the 3 recommended custom functions. You’ll need to strip and convert user input before returning the custom functions. Lastly, you’ll need to apply a simple math equation to get the correct percent.

## Conditionals

Next up are conditions, let’s tackle the psets for Week 1:

**[Deep Thought](https://cs50.harvard.edu/python/2022/psets/1/deep/)**: you can complete this within 5-6 lines of code, a single variable and one `if else` conditional statement. Note, you’ll need multiple conditions using logical operators for the single `if` statement, for help see [Python Operators](https://www.w3schools.com/python/python_operators.asp).

**[Home Federal Savings Bank](https://cs50.harvard.edu/python/2022/psets/1/bank/)**: a bit longer than `deep` at 7-8 lines of code and similar in logic, `bank` takes some more `elif` statements. Remember, if you want to use a character that python relies on, use `\\` to force it e.g. `'What\\'s up?'`.

<!-- <div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know. -->

 <!-- </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> -->
 
 **[File Extensions](https://cs50.harvard.edu/python/2022/psets/1/extensions/)**: ~15 lines of code can work for this pset, I used a lot of `elif` statements with a specific string method to check the end of the user input.

**[Math Interpreter](https://cs50.harvard.edu/python/2022/psets/1/interpreter/#math-interpreter)**: takes about 15 lines like extensions, similar in logic but I used a few more variables. For help, take the user input, assign them to variables and then perform some conditional logic with the math operators. You can assign multiple variables at once and use the `str.split()` function so they’re assigned correctly.

**[Meal Time](https://cs50.harvard.edu/python/2022/psets/1/meal/#meal-time)**: this is good to go on from math as it builds upon the same concepts like assigning multiple variables at once. You’ll need a couple more variables to make this pset work along with the condition, of course.

## Loops

Python has a powerful set of constructs to repeat or iterate values we pass to it.

Let’s look at Week 2:

**[camelCase](https://cs50.harvard.edu/python/2022/psets/2/camel/#camelcase)**: completed within 10 lines of code, this is the most nested of the psets so far, meaning there are more indented blocks of code. Relying heavily on the for loop (like most of the psets this week), you’ll need a couple more string methods like `str.isupper()` to complete this one.

**[Coke Machine](https://cs50.harvard.edu/python/2022/psets/2/coke/#coke-machine)**: the longest pset yet coming in at ~25 lines, there’s nothing new you haven’t used in the past psets besides a `while True` loop. Remember to start with checking the user input first before applying math to the variables.

**[Just setting up my twttr](https://cs50.harvard.edu/python/2022/psets/2/twttr/#just-setting-up-my-twttr)**: this is a fun one, coming in at about 10 lines for me, I used a simple `for` loop around an `if` condition to assess if a letter in a user string is a vowel.

**[Vanity Plates](https://cs50.harvard.edu/python/2022/psets/2/plates/#vanity-plates)**: this felt long a big leap forward, I recommend reading the instructions and listing all the steps. With nearly 50 lines of code, my program worked but was bloated and need reworking if I’m honest. Tip, it was easier to avoid slicing strings and focus on `if` conditions to match the beginning or end of the input.

**[Nutrition Facts](https://cs50.harvard.edu/python/2022/psets/2/nutrition/#nutrition-facts)**: longer than some psets at ~30 lines due to using a `dict`, I solved this one without using a loop… whoops. It goes to show there are many ways to make the cat meow. For help, I recommend making a simple `dict` and not simply copying the lecture’s example. A single `dict` is much easier than a `list` with multiple `dict`‘s.

## Exceptions

Here are my notes for Week 3’s lecture, be aware you’ll use all of the concepts outlined in the psets.

Exceptions: when things go wrong with code i.e. errors. `SyntaxError`: missing syntax, can’t solve itself, you must. `ValueError`: can’t understand value e.g. `string` ≠ `int`. `NameError`: incorrectly using your own code e.g. local/global vars.

`try` statement attempts to run code, `except` handles errors, `else` in case all else. Best practice: `try` only surrounds suspect code producing errors. `def` own function, `return` more powerful than `break`, can shorten code. `pass` catches error but ignores it.

Now let’s get into the psets:

**[Fuel Gauge](https://cs50.harvard.edu/python/2022/psets/3/fuel/#fuel-gauge)**: completed within 30 lines, it’s a good intro to applying `try` and `except`. After you check the user’s input, you’ll need to apply a bit of math to find the percentage of the given fraction, hint: divide each number and multiply by 100.

**[Felipe’s Taqueria](https://cs50.harvard.edu/python/2022/psets/3/taqueria/#felipes-taqueria):** in 20 lines of code, good exercise for understanding `dict` in more detail. Remember Week 2 info and all you need is to index the key’s value and add it to a variable.

**[Grocery List](https://cs50.harvard.edu/python/2022/psets/3/grocery/#grocery-list)**: following `taqueria` and stressing your `dict` skills, I completed this pset in less than 15 lines. Remember you can use a `for` loop with two iterative values, meaning you can use that to print both keys and values. Also, don’t forget to `print()` in a sorted fashion i.e. alphabetical.

**[Outdated](https://cs50.harvard.edu/python/2022/psets/3/outdated/#outdated)**: with less than 40 lines, this is another bloated monster that needs to be cut down… but it works! I looked at this as two functions, both matching each input allowed of dates, this is what makes the program so long. Essentially, take the input, pick a function, match it against its requirements and output in the new format. Tip, use the `index()` method to extract the location of the item as a number, you can `+1` so it doesn’t start at `0`.

Alright, now Week 3 psets have come and gone, the wait for Week 4 is on. Enjoy the learning (struggle) haha.

## Libraries

If interested, here’s my notes from W4’s lecture:

Libraries: generic term module/package, other code/programs avaliable for use. `modules`: library implimented in a file with functions/features built-in. `import <module>`: imports all functions/features within single module. `<module>.<function>()`: allows the use of function e.g. `random.choice(seq)` seq = list(like). `from <module> import <function>`: only imports single function from module. `<function>()`: if single function is called, module name can be removed e.g. `choice(seq)`. `sys.argv` (System Argument Vector): takes CL input/argument to use in program.

`packages`: (3rd party) library implemented in a folder e.g. [PyPi (Python Pacakge Index)](https://pypi.org/) &gt; [cowsay](https://pypi.org/project/cowsay/). `pip`: pre-built python program/packet manager for Python. API (Application Programming Interface): 3rd party services code can communicate with. `requests`: popular web requests module, pretends to be browser. JSON (JavaScript Object Notation): lang. agnostic format, non-dependant on JS, all lang. friendly.

With that out of the way, let’s get into the psets:

**[Emojize](https://cs50.harvard.edu/python/2022/psets/4/emojize/#emojize):** a lot easier than I expected being at W4, after `import` it can be completed in two lines of code. Make sure to read the documentation and use the right function from the `emoji` module.

**[Frank, Ian and Glen’s Letters](https://cs50.harvard.edu/python/2022/psets/4/figlet/#frank-ian-and-glens-letters):** this was a lot of fun as I’ve always liked ASCII Art. Really make sure to follow the `module` docs, it’s almost just a follow your nose situation. The only thing I’ll add is `sys.exit(1)` – you’ll know when you need it.

**[Adieu, Adieu](https://cs50.harvard.edu/python/2022/psets/4/adieu/#adieu-adieu):** I’ve never seen The Sound of Music so I’ve got no idea what’s going on. In confession, I didn’t use the `module` required but was still able to pass. Instead, I used a series of `methods` like `join()` and `replace()` which made it work… yes, I know it’s not right, but it’s what I got for now.

**[Guessing Game](https://cs50.harvard.edu/python/2022/psets/4/game/#guessing-game):** funny enough, I’ve completed a [similar project](https://mrash.co/beginner-python-project-guessing-game/) so this wasn’t too challenging. Really it’s just using the `random` `module` and its function with a few `try except` and `if elif else` statements.

**[Little Professor](https://cs50.harvard.edu/python/2022/psets/4/professor/#little-professor):** another good pset to stretch the custom function abilities, something I’m still struggling with. Focus on one function at a time, first `get_level()`, then `generate_integer()` and lastly `main()`. I completed it in about 40 lines of code, but I think it’s way to long for what it does.

**[Bitcoin Price Index](https://cs50.harvard.edu/python/2022/psets/4/bitcoin/#bitcoin-price-index):** after `professor` this was much easier, I used the same problem-solving method and am now understanding why custom functions are so valuable. I created `check_argv()` and `get_bc_value()` both serve there own abstracted purpose. Regarding using `json` I didn’t need to import `json` but just used `requests.get()` and then the `.json()` method. Don’t forget you can index by specifying the key, example `o['bpi']`.

## Unit Tests

I found Week 5 psets really hard and not as interesting as previous weeks. It’s worth taking your time to improve your code when reworking some previous psets. You’ll find it will deepen your understanding of earlier weeks. Also, no notes from me this week, see the [official notes](https://cs50.harvard.edu/python/2022/notes/5/).

**[Testing my twttr](https://cs50.harvard.edu/python/2022/psets/5/test_twttr/#testing-my-twttr)**: reworking `twttr` shouldn’t be too difficult for you at this stage. If you follow the lectures, writing the test\_twtter will be very doable, just take your time. Writing the `test_twttr` is also doable, don’t forget to `import` the function you’re testing and use `assert`.

**[Back to the Bank](https://cs50.harvard.edu/python/2022/psets/5/test_bank/#back-to-the-bank):** reworking `bank` left me with almost the same amount of lines, but more optimized and cleaner, I think. This pset is similar in spirit to `twttr`, again, take your time.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>**[Re-requesting a Vanity Plate](https://cs50.harvard.edu/python/2022/psets/5/test_plates/#re-requesting-a-vanity-plate)**: I saved this for last as [Vanity Plates](https://cs50.harvard.edu/python/2022/psets/2/plates/#vanity-plates) was really hard, originally 50+ lines of code. Reworking it to &lt;20 lines was a lot of fun and I gained a much deeper understanding.

**[Refueling](https://cs50.harvard.edu/python/2022/psets/5/test_fuel/#refueling):** the rework saved me ~10 lines of code, but for `test_fuel` make sure to use `pytest.raises()` to test for errors. Otherwise testing your functions is similar to the other test psets.

## File I/O

Alright, Week 6, file in out, let’s go. Here are my notes for the week:

Typically, python stores data in RAM (memory), until File Input/Output changes that. `open()` opens/reads file in a state e.g. `a` append, `w` write, `x` create, `r` read etc. `write()` writes to file, `close()` closes file. `with open('<file>') as variable:` can open and assign file, then close after block. `readlines()` method returns a list with each line is an item. `lambda` writing inline functions, no need to `def` custom function elsewhere.

`csv` module, apart of standard library, must `import`. `csv.reader()` reads csv files, can pass variable through. `csv.writer()` writes to csv files, can use `writerow([<value 1>, <value 2>])`. `csv.DictReader()` for `dict` uses `key: value` pair. `csv.DictWriter()` for `dict` uses `key: value` pair, specify `fieldnames=['1', '2']`. `PIL` pillow module, allows image manipulation, `from PIL import Image`.

Notes done, now let’s see the psets:

**[Lines of Code](https://cs50.harvard.edu/python/2022/psets/6/lines/#lines-of-code):** completed in ~30 lines of code, I used two functions 1) validate, and 2) find\_lines. Don’t forget you can declare new variables when you define a function.

**[Pizza Py](https://cs50.harvard.edu/python/2022/psets/6/pizza/#pizza-py):** around ~20 lines of code for this pset, two functions 1) validate, and 2) tab. To complete `pizza` use similar `sys.argv` code from the previous pset, and then a simple `for loop`. Make sure to read the `tabulate` docs for more detail.

**[Scourgify](https://cs50.harvard.edu/python/2022/psets/6/scourgify/#scourgify):** in about ~40 lines with again, two functions 1) validate, and 2) clean\_files, this time getting used to `csv.DictReader()`. Use `next()` to skip the heading, that could save you a lot of time, plus `writeheader()` too.

**[CS50 P-Shirt](https://cs50.harvard.edu/python/2022/psets/6/shirt/#cs50-p-shirt):** this was a lot of fun, moving from text/terminals to graphics/images is awesome. In approx ~30 lines, with again two functions of 1) validate, and 2) edit, this is all about the `PIL` library. You’ll need a few `if`, `elif` statements to validate and for the edit function use `ImageOps.fit()`.

## Regular Expressions

Great, now Week 7 RegEx (RE). I was worried about the increased difficulty of RE but glad to finally learn the language within the language. No custom notes from me so here are [the official notes](https://cs50.harvard.edu/python/2022/notes/7/).

**[NUMB3RS](https://cs50.harvard.edu/python/2022/psets/7/numb3rs/#numb3rs):** great introduction to RE, with about 7 lines of code and one function of validate. Ensure to `search()` your pattern, if it matches then use an `if` statement to check and return either `False` or `True`.

**[Watch on YouTube](https://cs50.harvard.edu/python/2022/psets/7/watch/#watch-on-youtube):** similar length as `numb3rs` with the single function, this time called parse. The difference compared to the previous pset is using two separate patterns of RE.

**[Working 9 to 5](https://cs50.harvard.edu/python/2022/psets/7/working/#working-9-to-5):** this ramped up in difficulty, about ~30 lines with a single RE pattern match, but over 9 `if` statements. Sure, my program passed but it could use some optimization. I took the group approach by splitting up the pattern match into multiple groups and then running conditions against them.

**[Regular, um, Expressions](https://cs50.harvard.edu/python/2022/psets/7/um/#regular-um-expressions):** after `work`, this was a nice break, in just 7 lines of code again, `um` was a simple pset. Use `findall()` for this one!

**[Response Validation](https://cs50.harvard.edu/python/2022/psets/7/response/#response-validation):** great use of the `validator_collection` library, and again just 7 lines of code with a single function. Make sure to read the docs linked and don’t overthink it.

## Object-Oriented Programming

Well Week 8 nearly broke me, I thought Unit Testing was a challenge, that was nothing compared to Object-Oriented Programming (OOP). In short, I passed all psets with significant assistance from a work colleague, CS50P staff and fellow students via Discord. I couldn’t have done it without them.

[**Seasons of Love**](https://cs50.harvard.edu/python/2022/psets/8/seasons/#seasons-of-love): ah, `seasons` I hate you, haha, no, you are a good learning experience. I’m not going to pretend like I fully understand classes, but a single `class` with five methods did the trick for me.

**[Cookie Jar](https://cs50.harvard.edu/python/2022/psets/8/jar/#cookie-jar):** in ~40 lines, this was extremely difficult like `seasons`, a single `class` with six methods. All I know is I need to rewatch the lecture, I’m sorry I am of no help here.

**[CS50 Shirtificate](https://cs50.harvard.edu/python/2022/psets/8/shirtificate/#cs50-shirtificate):** this was actually a nice last pset as it was a bit challenging but pretty straightforward. After the last two psets, I think it was nice to end on an easier one imo. Less than 20 lines, just a single main function and six methods from `FPDF()` – and that’s it!

## Et Cetera

No psets for this week, just the final project, how exciting! Stay tuned as I’ll be writing a full breakdown of [my final project](https://www.youtube.com/watch?v=KoEHd3VtJ9E) along with a course review and reflection.

Thanks for reading and I hope you learned something from this little exercise. This is days 48, 49, 51 and 55 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.