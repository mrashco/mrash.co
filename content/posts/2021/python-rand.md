---
title: "Random Number Generator \u2022 Easy Python Project"
author: Mr Ash
type: "post"
published: 2021-10-17
lastUpdated: 2022-11-04
url: "/random-number-generator-easy-python-project/"
image: https://images.unsplash.com/photo-1502570149819-b2260483d302?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzQ0MTU0OTM&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1707
categories: Programming
tags:
    - Python
    - Automate The Boring Stuff
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Random-Number-Generator--Easy-Python-Project-e18sqms" width="400px"></iframe> -->

Want an easy python project to get you started learning python?

Here’s a random number generator built-in python!

See the project live below or via [GitHub](https://github.com/mrashleyball/Random-Number-Generator).

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/Random-Number-Generator?lite=true" width="100%"></iframe>

Okay, let’s build your very own number generator python program.

## Foundation

Let’s write the program in stages.

But first, it’s recommended to write out pseudo code as it helps to map out and plan the program before you deep dive into writing it.

```python
# Random Number Generator

# 0 Import module
# 1 User selects start and end numbers
# 2 Validate user input
# 3 Handle error messages i.e user inputs strings
# 4 Create random number
# 5 Display random number
```

Okay, here’s stage one.

```python
import random

number = random.randrange(1,10)

print('Your random number is: ' + str(number))
```

Import the random module to allow for random numbers, then assign a random number between 1 and 10 to the variable number. Lastly, display a concatenated string with the variable number converted into a string.

## Adding User Input

Now let’s beef it up a bit and get user input.

```python
import random

startNumber = int(input('Select your starting number: '))
endNumber = int(input('Select your end number: '))

number = random.randrange(startNumber,endNumber)

print('Your random number is: ' + str(number))
```

Here are two more variables, `startNumber` and `endNumber`, they both ask for user input which is passed through the integer conversion function.

## Validating User Input

Asking for user input is great, but how do we validate that user input?

First, create a `while` loop set to `True` this means it will continue in a loop until a `break` statement. This is perfect if the user inputs incorrectly, they’ll always go back and be asked for the correct input.

Then it’s a case of giving `print()` messages based on what they’ve done wrong. Do this with `if` and `elif` statements, one for numbers less than zero, if numbers are the same and the start number higher than the end number.

```python
import random

while True:
    startNumber = int(input('Select your starting number: '))
    endNumber = int(input('Select your end number: '))
    if startNumber < 0:
        print('Start Number cannot be less than zero. Try again.')
    elif startNumber == endNumber:
        print('Start and End numbers cannot be the same. Try again.')
    elif startNumber >= endNumber:
        print('Start Number cannot be higher than End Number. Try again.')
    elif startNumber <= endNumber:
        break

number = random.randrange(startNumber,endNumber)
print('Your random number is: ' + str(number))
```

## Handling Error Messages

What is the user types in letters, not numbers?

Because we’re passing the `input()` through an `int()` conversion, then strings, or letters, will produce a `ValueError`. So to handle error messages without the program crashing and closing, we can use `try` and `except`.

```python
import random

while True:
    try:
        startNumber = int(input('Select your starting number: '))
    except ValueError or NameError:
        print('Error! Numbers only.')
    try:
        endNumber = int(input('Select your end number: '))
    except ValueError or NameError:
        print('Error! Numbers only.')
    
    try:
        if startNumber < 0:
            print('Start Number cannot be less than zero. Try again.')
        elif startNumber == endNumber:
            print('Start and End numbers cannot be the same. Try again.')
        elif startNumber >= endNumber:
            print('Start Number cannot be higher than End Number. Try again.')
        elif startNumber <= endNumber:
            break
    except NameError:
        print('Error, try again.')

number = random.randrange(startNumber,endNumber)
print('Your random number between ' + str(startNumber) + ' and ' + str(endNumber) + ' is: ' + str(number))
```

Oh, and for the last display message showing the random number, also update it to incldue both the starting and ending number.

## Reflection

The idea of this mini-program came from a guessing game that uses the same random module.

I wanted to try to create something with more user input.

The only tricky thing I had to get my head around again was error handling. I understood the concept of try and except, but applying it was tricky.

I also enjoyed doing this program in stages. I got the idea from work, a colleagues son wrote an example for a program in this way.

I think breaking up a program into separate files shows progression. Combine that with well-written comments and it makes for a great learning project.

Even small projects with 40+ lines of code can be a bit confusing at first to newcomers, like me. If the lines gradually increase, then it becomes more understandable.

Overall, this was a fun little project that only took 10 to15 minutes to program. I’m getting quicker at idea, plan, program, finishing and publishing. It’s fun to see the concepts sink in with each new program.

Learning python has easily been the funniest programming language I’ve learnt.

This is Day 25 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.