---
title: "Intro To Python \u2022 Free Python Starter Guide"
author: Mr Ash
type: "post"
published: 2021-10-09
lastUpdate: 2022-11-04
url: "/intro-to-python-free-python-starter-guide/"
image: https://images.unsplash.com/photo-1538439907460-1596cafd4eff?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzM3NTQ3Mzg&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1735
categories: Programming
tags:
    - Python
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Intro-To-Python--Free-Python-Starter-Guide-e18hhsb" width="400px"></iframe> -->

Wanting to learn Python?

Of course you do!

Python is the hacker’s language, it’s more modern than bash and it’s super cool.

If you’ve never programmed or wrote a line of code, that’s okay! We all have to start somewhere.

There’s a lot of good places to learn Python, I recommend [Automate The Boring Stuff with Python](https://automatetheboringstuff.com/) and the official [Python Documentation Tutorial](https://docs.python.org/3/tutorial/).

If you’re learning to hack in the Cyber Security space, see [Hackers Learning Path](https://mrash.co/learning-path-for-beginner-hacker/). For some project ideas, try [Guessing Game](https://mrash.co/beginner-python-project-guessing-game/) and [Is It Raining?](https://mrash.co/basic-python-project-is-it-raining/)

*Disclaimer, you’re expected to have basic computing and operating system skills, ideally Linux.*

## Mindset: How To Python

Think about Python like any language, take English for example. There’s rules around what words can be used, their meaning, the structure of sentences and more.

All these elements are predefined and make it possible for us to learn and communicate with fellow English speaking humans.

Python is the same concept, you need to learn the rules, meanings and structure to communicate, or, create a program. Instead of humans, programming languages like Python are designed to communicate with computers.

A couple of other notes, programs are a series of instructions, programmers don’t need to know much math, you’re never too old to learn programming and programming is a creative activity.

## Setup: Starting With Python

Start at [python.org](http://python.org) and [download the latest version](https://www.python.org/downloads/) of the language, then use the [Beginners Guide](https://wiki.python.org/moin/BeginnersGuide) to see the options at work. Next, download a code editor, aka [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment), there are lots of options out there, I recommend [Visual Studio Code](https://code.visualstudio.com/). For more on Python, see [Python in Visual Studio Code](https://code.visualstudio.com/docs/languages/python#_run-python-code).

Once vscode is installed, install some extensions, use `CTRL + SHIFT + x` and type `python` it should be the first search result, just double check it’s the official extension from Microsoft.

![https://p146.p4.n0.cdn.getcloudapp.com/items/5zu9ZkyB/290b5685-f4c6-41b5-8169-7a4c51d4a9f9.jpeg?v=0b659d02ff3a81026b574d6721d5d2fe](https://p146.p4.n0.cdn.getcloudapp.com/items/5zu9ZkyB/290b5685-f4c6-41b5-8169-7a4c51d4a9f9.jpeg?v=0b659d02ff3a81026b574d6721d5d2fe)

While you’re there, optionally install [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) and [GitHub](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github).

Okay, let’s set up your folder structure, press `CTRL + K O`, create a new folder where ever you like, if you’re unsure, go to Documents and call it `Intro To Python - Mr Ash`.

![https://p146.p4.n0.cdn.getcloudapp.com/items/OAuG9ynQ/eee5c43d-ecb3-479f-a827-21fe00e43a43.jpeg?v=5d63a23512182ab8f16c63e6739aa911](https://p146.p4.n0.cdn.getcloudapp.com/items/OAuG9ynQ/eee5c43d-ecb3-479f-a827-21fe00e43a43.jpeg?v=5d63a23512182ab8f16c63e6739aa911)

Now, let’s create your first python program, press `CTRL + N` to create a new file, then name it `hello.py`. The `py` is the python file extension, vscode will automatically detect it’s a python file and save it as so.

![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuPYD66/83fc6341-ef30-42ec-914a-1775f74012cc.jpeg?v=33b4c4ad595fb892c785b3a7e6e06974](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuPYD66/83fc6341-ef30-42ec-914a-1775f74012cc.jpeg?v=33b4c4ad595fb892c785b3a7e6e06974)

Now, line 1, type out `print('hello, world...')` – this is a tradition in programming. We’ll break down what is happening, but for now, just type it out and hit `CTRL + S` to save the file.

Let’s execute (or run) our new program and see the output. Type `CTRL + “ (that’s a tick back, it’s on the top left of your keyboard) to bring up the terminal.

Type `CTRL + SHIFT + P` to show the Command Palette, then type `python run` and hit enter on `Python: Run Python File in Terminal`, thanks to [this article](https://jasonmurray.org/posts/2020/vscodeplay/) for your help.

Your output should be the following:

![https://p146.p4.n0.cdn.getcloudapp.com/items/geupve7R/bfad75f0-f833-4d6e-a0cf-c74c6706ce1f.jpeg?v=e9cde301ebc5e328a65590bd3957537e](https://p146.p4.n0.cdn.getcloudapp.com/items/geupve7R/bfad75f0-f833-4d6e-a0cf-c74c6706ce1f.jpeg?v=e9cde301ebc5e328a65590bd3957537e)

If something is wrong, that’s okay, welcome to bug squashing. There’s something wrong with your code, it’s not running as intended, it may be something small, like a spelling error or depending on the size of your program, an entire misconfiguration.

If all is well, great! Your first program is complete, congrats.

The program you just built is using is an expression, with the function `print` with a `string` value. I know this doesn’t mean much right now, just stick with me.

Python has built-in functions, they’re like pre-built programs inside your program. It allows you to not have to write EVERYTHING from scratch. So, `print()` is the function that prints out, it’s followed by brackets, anything inside those brackets is considered an input for the function.

In this case, we’ve passed `'hello, world...'`, now this is a `string`, one of the most common data types, we’ll talk more about data types soon. Think of a `string` like a normal sentence, a mixture of characters including letters, spaces and/or numbers. You could put almost anything into a string, just make sure you have formatted it as so, `'string goes here'`.

Okay, still with me? Great!

## Basics • Core Python Elements

Okay, to see Python in action, we’re going to change it up slightly. Instead of creating a new file, we’re going to use an interactive shell, you’ll see what I mean.

Bring up the Command Palette with `CTRL + SHIFT + P`, and type `python start`, then select `Python: Start REPL`, REPL is short for Read, Eval, Print and Loop, [read more](https://pythonprogramminglanguage.com/repl/) if interested, and thanks to [this article](https://stackoverflow.com/questions/61808776/how-do-i-open-the-interactive-shell-repl-in-visual-studio-code).

![https://p146.p4.n0.cdn.getcloudapp.com/items/o0u7o0rG/b4a91435-e673-415a-b60d-7a1ae5de15e2.jpeg?v=1ad48cb644222bb6200cf11dbfd74964](https://p146.p4.n0.cdn.getcloudapp.com/items/o0u7o0rG/b4a91435-e673-415a-b60d-7a1ae5de15e2.jpeg?v=1ad48cb644222bb6200cf11dbfd74964)It might take a second, but you’ll notice the terminal change, this is the interactive shell.

Try your previous program, now all in one line `print('hello, there...')` and hit `ENTER`. You should see your `string` printed on the next line.

If you’re wondering, you don’t write complete programs here, this is for testing purposes and learning, like us!

Okay, type a new expression `2 + 2` and hit `ENTER`, I bet you can guess the output.

Let’s break down what’s happening. This expression includes two values, `2` and a single operator, `+`. The `2` values have an `Integer` data type, more on them soon, I promise.

Python evaluates to a single value, in this expression it’s `4`, but no matter how complex a python program is, it always evaluates to a single value. You can always make a value evaluate to itself, simply type `2` and hit `ENTER`. For more, see [Using Python as a Calculator](https://docs.python.org/3/tutorial/introduction.html#using-python-as-a-calculator).

Okay, so let’s learn some more elements that make up Python, we’ll do this by writing another small program.

You can switch between shells, or terminals, by selecting Python on the right.

![https://p146.p4.n0.cdn.getcloudapp.com/items/OAuGK6D5/06f927b0-553a-4816-bcf8-a94fd15dbf02.jpeg?v=8f894729cb36806562bfb583036f61ce](https://p146.p4.n0.cdn.getcloudapp.com/items/OAuGK6D5/06f927b0-553a-4816-bcf8-a94fd15dbf02.jpeg?v=8f894729cb36806562bfb583036f61ce)The best way to start is always with pseudo code, this is like a plan or outline for what you expect the program to do.

1. Say hello, ask for name.
2. Print hello with name.

So here’s the following program:

```python
print('Hello, world...') # Print hello
name = input('What\\'s your name? ') # Ask for name
print('Hello ' + name) # Say hello with name
```

Don’t forget to use the Command Palette to run the program, `CTRL + SHIFT + P` and type `run`.

![https://p146.p4.n0.cdn.getcloudapp.com/items/GGu4Plke/8e725563-7f66-47f8-ad02-e5d3937a8e10.jpeg?v=5b5eba7fa20120ea8dc64a4914661c06](https://p146.p4.n0.cdn.getcloudapp.com/items/GGu4Plke/8e725563-7f66-47f8-ad02-e5d3937a8e10.jpeg?v=5b5eba7fa20120ea8dc64a4914661c06)The program will say hello, ask for your name and then say hello again with your name.

Let’s break this down, if you see `#` anything after is a comment, this is for humans, not computers. The python interpreter will see and ignore comments.

Next, on line 2, `name` is a variable, we could call the variable any title, but because the word name easily describes what’s stored in the variable, it’s a good title for it.

Think of variables like a box, we can store any value or data type inside of it. In this program, we’re storing the input from the user. `input()` is another built in function like `print()` but as you experienced, it’s waiting for user interaction or input.

Line 3, uses `print()` again but this time it’s using string concatenation, big word, it just means to combine multiple elements.

Visual Studio Code is great, like most code editors, it automatically colour codes each element of your program. In my case, variables are blue, comments are green, functions are yellow, string data types are orange and white is general syntax. Syntax just means the brackets and characters that Python uses to understand what we’re telling it to do.

Let’s learn some new data types and add them to our program. Add the following to lines 5 and 6:

```python
age = input('What\\'s your age: ')
print(age)
```

![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuj4qOm/a21ffeaa-7054-457c-962c-94d471ed8823.jpeg?v=f6b3ff255d294a86abafd2f26fd4482e](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuj4qOm/a21ffeaa-7054-457c-962c-94d471ed8823.jpeg?v=f6b3ff255d294a86abafd2f26fd4482e)So we’ve added a new variable called `age`, it’s now going to be an integer data type. Integers are whole numbers like 20, 21, 50 etc.

The output for `age` should be whatever you type in when asking. Now let’s use some more concatenation, let’s edit line 6 to look like the following:

```python
print("You're " + str(int(age) + 1) + " next year.")
```

Let’s take a look at what we’ve added here. We’re using two functions inside of our `print()` function, there’s `str()` and `int()` these are known as conversion functions. Meaning, anything that get’s passed through them will be converted into their data type. This is important when we want to combine multiple data types. Python needs to know each data type, and they need to be converted into a string.

So the `age` variable is converted into an integer, a whole number, it adds one, and then it’s converted into a string, which is normal characters, then it’s combined with the other strings to form an entire sentence.

Remember, Python always evaluates to a single value. In this case, the sentence of strings is the single value. It seems complicated at first, but after a few tries it makes more sense, don’t worry if it’s not all sticking just yet.

## Basic Projects (Coming Soon)

This is Day 21 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.