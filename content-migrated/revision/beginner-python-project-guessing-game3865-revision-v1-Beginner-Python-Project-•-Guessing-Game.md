---
id: 4681
title: "Beginner Python Project \u2022 Guessing Game"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4681
url: "/?p=4681"
---

Do you want a beginner Python project to keep you on your programming journey?

Here’s a breakdown of a simple Guessing Game made in Python.

<div class="wp-block-image"><figure class="alignleft size-large is-resized">[![](https://p146.p4.n0.cdn.getcloudapp.com/items/5zuBb0rz/52c5e92a-fa3b-410b-b057-b3cbdf935412.jpeg?v=bf40ee3f13a67d04aa8a03dde650ae86)](https://replit.com/@MrAshleyAshley/Guessing-Game-Automate-The-Boring-Stuff-Python-Programming-C#guessing_game.py)</figure></div>See it live via [Replit](https://replit.com/@MrAshleyAshley/Guessing-Game-Automate-The-Boring-Stuff-Python-Programming-C#guessing_game.py) or view the source code via [GitHub](https://github.com/mrashleyball/Guessing-Game-Automate-The-Boring-Stuff-Python-Programming-Course).

Full disclosure, this is a part of the [Automate The Boring Stuff](http://automatetheboringstuff.com/) with Python Programming Course.

## Plan the Program with Pseudocode

Pseudocode is like a programmer’s brain dump.

Write out a simple list of the steps this guessing game will go through.

The point of this is to think of each step to better understand what code to write.

Guessing Game Pseudocode:

1. Print hello message, ask for **name**
2. Accept user input as name
3. Print instructions + name
4. Set random number to **guess**
5. Set guess **limit** to six
6. Loop each guess
7. Accept user input as guess
8. Increase guess limit by one
9. Detect if guess is higher or lower
    1. If lower, print too low message
    2. If higher, print too high message
10. If correct, break
11. If correct, print ‘you won’ message
12. Else, print the answer i.e. random number

Pseudocode can be edited later as your program can change, but it’s the best place to start.

It should be in the exact same order as if the program was executing it.

Try and edit your pseudocode to make the most simple version of the program.

I like to **bold** the variables to help my brain figure out where to start, it’s optional.

## Program Step By Step

Start by adding a comment using the `#` with a title to describe the app.

```
<pre class="wp-block-code">```
# Guessing Game - Automate The Boring Stuff with Python Programming Course
```
```

In order to use a random number later, we’ll need to use a function from the random module.

```
<pre class="wp-block-code">```
import random
```
```

Now let’s create a welcome message and ask for the user’s name.

```
<pre class="wp-block-code">```
print("Hi there, what\\'s your name?")
name = input("Your name: ")
```
```

Lastly, use the name of the player and give them the game instructions.

```
<pre class="wp-block-code">```
print ("Hi " + name + ", I\\'m thinking of a number between 1 - 10, what is it? (You have six guesses)")
```
```

We need to set the random number to a variable, in this case, it’s `x` but you can call it anything.

Since we imported the random module, we can use the `randit` function to set the random number. In this case, set it between 1 and 10.

Then set the number of guesses to 6.

```
<pre class="wp-block-code">```
x = random.randint(1,10) # Set random number to guess
limit = 6 # Set guess limit to six
```
```

Now the meat of the program, detecting if the user’s guess is correct or not and indicating if it’s lower or higher.

The `for` loop is perfect for repeating code a set number of times via the `range()` function. By setting it to `(1,7)` you’ve set the six guess limit.

The `if` statement checks the guess is lower, the `elif` checks if it’s higher, otherwise the `else` passes it off to `break` as it’s correct and ends the loop… or the guess limit is reached.

```
<pre class="wp-block-code">```
# Detect if higher or lower
for limit in range(1,7):
    guess = int(input())
    if guess < x:
        print("That's lower.")
    elif guess > x:
        print("That's higher.")
    else: break # Stop once correct guess
```
```

Lastly, either the guess is equal to the random number or not and a simple `if else` statement determines the message to display.

```
<pre class="wp-block-code">```
if guess == x: # Display win/loss message
    print("Correct! You got it! Nice work " + name + ", the number is " + str(x))
else:
    print("Better luck next time, " + name + ", the random number is " + str(x))

```
```

If you have feedback, please send me a message via [Twitter](https://twitter.com/mrashleyball).

This is Day 8 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.