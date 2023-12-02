---
title: "ZigZag - Beginner Python Project"
author: Mr Ash
type: "post"
published: 2021-10-19
lastUpdated: 2022-11-04
url: "/zigzag-beginner-python-project/"
image: /wp-content/uploads/2021/10/background.jpg
categories: Programming
tags:
    - Python
    - Automate The Boring Stuff
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/ZigZag--Beginner-Python-Project-e1906et" width="400px"></iframe> -->

Let’s learn some Python!

Want an easy python program to get started? Here’s zigzag.

This program is from [Automate The Boring Stuff With Python Chapter 3](https://automatetheboringstuff.com/2e/chapter3/), under A Short Program: Zigzag.

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/ZUcippDDBh8?feature=oembed" title="Zig Zag • Beginner Python Project • Automate The Boing Stuff With Python • Study Session #3 (lofi)" width="800"></iframe></div></figure> -->

Welcome to my third study session to learn Python Programming! The video above covers the entire process of copying the zig zag program from Automate The Boring Stuff With Python.

See [Built-in Functions](https://docs.python.org/3.4/library/functions.html#print), [Time access and conversions](https://docs.python.org/3/library/time.html) and [What does end=’ ‘ exactly do?](https://stackoverflow.com/questions/20372485/what-does-end-exactly-do)

## 1. Program

See the complete program below, feel free to copy this.

```python
import time,sys 
indent = 0 # Amount of spaces to indent
indentIncreasing = True # Increase or not

try:
    while True: # Main program loop
        print(' ' * indent, end='')
        print('********')
        time.sleep(0.1) # Pause for 1/10

        if indentIncreasing:
            # Increase number of spaces
            indent = indent + 1
            if indent == 20:
                # Change direction
                indentIncreasing = False
        
        else:
            # Decrease number if spaces
            indent = indent - 1
            if indent == 0:
                # Change direction (again)
                indentIncreasing = True
except KeyboardInterrupt:
    sys.exit()
```

For a full writeup and breakdown of each stage in the program, see the official [A Short Program: Zigzag](https://automatetheboringstuff.com/2e/chapter3/).

## Reflection

This was a really quick and easy program to copy and deconstruct, it’s worth doing it yourself.

I learnt about the `time` module and I’m getting more comfortable looking up modules from the standard library. Thank goodness for great online documentation!

It’s also good to see the `try/except` statement in use again. It’s a pretty straightforward statement in Python I’ve got my head around.

I still don’t have a complete grasp on the line `print(' ' * indent, end='')` – even after reading up about the print function again, it hasn’t really clicked for me just yet.

This short program reminded me of the start of [CS50x](https://cs50.harvard.edu/), a fantastic computer science course! I started it and failed to program, so I’ll be going back to that in the future. This program and learning Python, in general, is giving me the confidence to do it!

This is Day 27 of [#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.

{{<youtube ZUcippDDBh8>}}