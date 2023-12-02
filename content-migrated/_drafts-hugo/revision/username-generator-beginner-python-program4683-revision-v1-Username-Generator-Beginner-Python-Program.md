---
id: 4691
title: Username Generator | Beginner Python Program
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4691
url: "/?p=4691"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Username-Generator--Beginner-Python-Program-e18s80g" width="400px"></iframe>Usernames, we all have one, maybe for work or on Twitter.

How about a python program that automatically generates a username based on your name?

Sound cool? Let’s make a simple project to generate usernames.

See the live program below:

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/Username-Generator?lite=true" width="100%"></iframe>*Disclaimer, this is not a python tutorial, for that, see [Intro To Python](https://mrash.co/intro-to-python-free-python-starter-guide/).*

## 1. Core Code

Let’s get the core elements down for the username generator.

First, displaying the title via `print()` and then using two variables with `input()`. Then at the end, `print()` the concatenated string to combine the variables.

We’ll just comment the slicing out for now and tackle that at the next stage.

```
<pre class="wp-block-code">```
print('Welcome to the Username Generator Program.')

first = input('Enter first name: ')
last = input('Enter last name: ')

# Slicing done here

print('Your username is: ' + last + first)

```
```

## 2. Slicing

Great, let’s slice out the sections of user input we need to create the username.

Now the username is based on the basic nomenclature of using the first four letters of the last name, and the first letter of the first name.

In order to program python to do this, we need to use slices.

We’ll assign the `first` and `last` variables with their sliced counterparts.

For the `last` variable, it starts at the first character, `0` up to but not including `4`. Then, get the first letter from the `first` variable by stating `0`.

That’s it!

```
<pre class="wp-block-code">```
print('Welcome to the Username Generator Program.')

first = input('Enter first name: ')
last = input('Enter last name: ')

last = last[0:4] # Slice first letter up to but not including 4 
first = first[0] # Slice first letter, starting at 0

print('Your username is: ' + last + first)

```
```

Thank you to [w3schools](https://www.w3schools.com/python/python_strings_slicing.asp).

## 3. String Conversion

The last step is to convert the concatenated output to lower case characters.

Generally, usernames are in lower case, plus this is good practice to use the `str.lower()` function.

```
<pre class="wp-block-code">```
print('Welcome to the Username Generator Program.')

first = str(input('Enter first name: '))
last = str(input('Enter last name: '))

last = last[0:4] # Slice first letter up to but not including 4 
first = first[0] # Slice first letter, starting at 0

print('Your username is: ' + str.lower(last) + str.lower(first)) # Change to lower case for username format

```
```

Thank you to [educba](https://www.educba.com/lowercase-in-python/).

## 4. Reflection

This was a fun small project I thought of when I woke up this morning.

It’s a popular username format so it’s fun thinking about how to automate its creation. I can imagine this built into a workplace app to spit out the new hire’s username.

It’s my first time using slices outside following walkthrough projects from Automate The Boring Stuff with Python, so I’m surprised I got it so quickly.

This program only took a few minutes to complete, a lot faster than I was expecting.

This is Day 24 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.