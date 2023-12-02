---
title: "Mad Lib Game \u2022 Beginner Python Project"
author: Mr Ash
type: "post"
published: 2021-10-11
lastUpdate: 2022-11-04
url: "/mad-lib-game-beginner-python-project/"
image: https://images.unsplash.com/photo-1597392582469-a697322d5c16?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzM4NTUyMzM&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1707
categories: Programming
tags:
    - Python
---

<!-- <iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Mad-Lib-Game--Beginner-Python-Project-e18k0hh" width="400px"></iframe> -->

Are you learning Python? Need some beginner Python projects?

It’s nice to have you here, this is my Mad Lib Game, an easy beginner Python Project for you!

[Mad Libs](https://en.wikipedia.org/wiki/Mad_Libs) are a simple game, it consists of one player prompts others for a list of words to substitute for blanks in a story before reading aloud.

Instead of a human, we’ll have the computer read them back via the terminal, cool.

Run it below by pressing on the green arrow.

<iframe frameborder="0" height="350px" loading="lazy" src="https://replit.com/@mrashleyball/MadLib-Game?lite=true" width="100%"></iframe>

If the embedded project above doesn’t work, here’s the project link: [](https://replit.com/@mrashleyball/MadLib-Game)<https://replit.com/@mrashleyball/MadLib-Game>

*Disclaimer, for a full Python guide, see [Intro To Python](https://mrash.co/intro-to-python-free-python-starter-guide/). For more Python projects, see [Is It Raining?](https://mrash.co/basic-python-project-is-it-raining/) and [Guessing Game](https://mrash.co/beginner-python-project-guessing-game/).*

## Pseudo Code

It’s a good idea to plan out your program, no matter the size!

Pseudo Code helps out-think like the program, step by step, how will the computer interpret your written instructions?

Here’s the PS Code for the Mad Lib game:

```python
# Mad Lib Game
# 1 Display title
# 2 Ask for name various inputs
# 3 Display combined output
```

It’s very simple, but it works really well.

Give your program a simple title followed by an outline of steps required for the program to operate. In this case, there’s really two important steps, #2 Asking for input, and #3 displaying combined output.

Also, make up your Mad Lib sentence, I made a fictitious scenario like so:

```python
# Yesterday, {name} walked into a {place}, I noticed they we're {verb} and had a {noun}. "How strange? I thought". So I asked them, what are you doing? They responding, "I'm {adjective}". Okay then...
# And then today, I saw {name2}, at the most {adjective2} {place2}. They we're {adverb} {verb2}... isn't that {adjective3}!
```

Lastly, let’s display the title of the game for the player:

```python
print('''Welcome to the Mad Lib Game.
You're going to receive a series of inputs, type whatever you like.
Ready? Great!
''')
```

Something of interest here, is three single quotations allow for multi-line strings, it’s good for writing larger sentences.

## User Input

Now the player has seen the game title and instructions, let’s get their input.

Below is the following code for names, places, verbs, nouns, adjectives and adverbs:

```python
name = input('Enter name: ')
place = input('Enter place: ')
verb = input('Enter verb: ')
noun = input('Enter noun: ')
adjective = input('Enter adjective: ')
name2 = input('Enter another name: ')
adjective2 = input('Enter another adjective: ')
place2 = input('Enter another place: ')
adverb = input('Enter an adverb: ')
verb2 = input('Enter another verb: ')
adjective3 = input('Enter another adjective: ')
```

Each input function is assigning user strings to a variable with a logical name. When variables doubled up, simply add a 2, or 3 to avoid multiple variables with the same name.

If you’re like me, and barely passed English in school, then here’s a quick reminder of [each element](https://schooltutoring.com/help/parts-of-speech-nouns-verbs-adjectives-and-adverbs/).

- **Noun**, a place, person or thing, e.g. decision, creation or sadness.
- **Verb**, a doing word, e.g. decide, create or sadden.
- **Adjective**, a describing word, e.g. decisive, creative or sad.
- **Adverb**, describes verbs, e.g. decisively, creatively or sadly.

## Output

Great, so now the user has filled in their Mad Lib inputs, now it’s time to display the output:

```python
print('Great work, here\'s the Mad Lib:')
print('Yesterday, ' + name + ' walked into ' + place + ', I noticed they we\'re ' + verb + ' and had a ' + noun + '. "How strange? I thought". So I asked them, what are you doing? They responding, "I\'m ' + adjective + '". Okay then...')
print('And then today, I saw ' + name2 + ', at the most ' + adjective2 + ' ' + place2 + '. They we\'re ' + adverb + ' ' + verb2 + '... isn\'t that ' + adjective3 + '!')
```

First, printing a generic message, then using string concatenation to combine the variable string input from the user to the string sentences.

## Reflection

The Mad Lib game is an ideal start python project in my opinion.

It’s enforcing variables, input functions, print functions and string concatenation, all core elements to Python. And it’s fun! My wife and I spent ages putting our friend’s names, celebrity names and others into wacky situations.

It’s the sort of project that isn’t too mind-bending for a beginner while also being enjoyable, a great mix while starting the python programming journey.

I think to make the game more complex, there could be a menu system introduced. The player could select from various sentences, they could play a short and simple game or a longer one.

There also could be a help menu introduced, at any time, if the user enters ‘help’, a list of explanations of nouns, verbs and adjectives could display.

Even the ability to go back would be a great addition, I noticed my wife entered a noun as a verb accidentally and wanted to change it before continuing. A back option would make that work well.

Overall, it’s simple and works well, perfect to pick up and try yourself while starting out with Python.

This is Day 22 of [#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.