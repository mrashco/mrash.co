---
id: 4726
title: "Bagels \u2022 Beginner Python Project"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4726
url: "/?p=4726"
---

Want a beginner Python Project that’s going to test you? A program longer than 40 lines of code?

Look no further, here’s Bagels!

This is from [The Big Book of Small Python Projects](https://inventwithpython.com/bigbookpython/) – [Chapter 1 Bagels](https://inventwithpython.com/bigbookpython/project1.html).

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/Bagels?lite=true" width="100%"></iframe>Watch the [Study Session #2](https://youtu.be/Fg_EoUtCfOU) for the full programming behind the scenes.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/Fg_EoUtCfOU?feature=oembed" title="Bagels • Beginner Python Project • Big Book of Small Python Projects • Study Session #2 (LoFi Chill)" width="800"></iframe></div></figure>*Disclaimer, some areas of this blog post are still under construction, look for Work In Progress (WIP).*

## 1. Global Variables, Main Function

Let’s break Bagels down.

First, import the random module and set two global variables.

`numDigits` sets the number of digits for the player to guess. Then `maxGuesses` sets the maximum amount of guesses the player can take before the game is over. Both of these can be adjusted.

```
<pre class="wp-block-code">```
import random
numDigits = 3
maxGuesses = 10

```
```

Let’s add the main function and print the instructions for the player.

```
<pre class="wp-block-code">```
def main():
		print(''' 
		
		I am thinking of a {}-digit number. Try to guess what it is.
		Here are some clues:
		When I say:    That means:
		Pico         One digit is correct but in the wrong position.
		Fermi        One digit is correct and in the right position.
		Bagels       No digit is correct.
		I have thought up a number.
		    You have 10 guesses to get it.
		'''.format(numDigits))

```
```

## 2. Main Game Loop

```
<pre class="wp-block-code">```
while True:
		secretNum = getSecretNum()
		print('I have thought up a number.')
		print(' You have {} guesses to get it.'.format(maxGuesses))

```
```

Let’s set the number of guesses to 1 and create a `while` loop, as long as the number of guesses is less than or equal to the max number of guesses the player can continue.

The `guess` variable is declared as a blank string so this makes it usable later in the program. If guess was declared inside the `while` block, then it would be local to that block only.

```
<pre class="wp-block-code">```
numGuesses = 1
        while numGuesses <= maxGuesses:
            guess = ''
            while len(guess) != numDigits or not guess.isdecimal():
                print('Guess #{}: '.format(numGuesses))
                guess = input('> ')

```
```

Next, creating a `clues` variable set to the function `getClues` which passes `guess` and `secretNum` through it. Then, assign and increase `numGuesses` by 1.

```
<pre class="wp-block-code">```
						clues = getClues(guess, secretNum)
            print(clues)
            numGuesses += 1

```
```

Now, let’s add an `if` statement to check the player’s guess, compare `guess` to `secretNum` and if it matches or is equal too, `break`.

Then let the player know they’re out of guesses by an `if` statement comparing `numGuesses` to be greater than `maxGuesses`.

```
<pre class="wp-block-code">```
if guess == secretNum:
                break
            if numGuesses > maxGuesses:
                print('You ran out of guesses.')
                print('The answer was {}.'.format(secretNum))
        print('Do you want to play again? (yes or no)')

```
```

Lastly, give the option to the player to play again now they’ve run out of guesses. If the player doesn’t input the letter ‘y’ or a word that starts with ‘y’, then a `break` statement is used and the program displays a final message.

```
<pre class="wp-block-code">```
 				if not (input('> ').lower().startswith('y')):
            break
    print('Thanks for playing!')

```
```

## 3. Functions (WIP)

Let’s take a closer look at our two custom functions, `getSecretNum` and `getClues`.

So, first set a new variable `numbers` and assign the numbers from 0 to 9 as a string through the `list()` to convert them. Then using the random module, pass `numbers` through and shuffle the order.

```
<pre class="wp-block-code">```
def getSecretNum():
    numbers = list('0123456789')
    random.shuffle(numbers)

```
```

Alright, now let’s define another new variable `secretNum` to a blank string. Then, in order to set the `secretNum` let’s use a `for` loop. In this case, `i` is a local variable which only works inside this `for` loop. The `range()` is set to the original variable `numDigits` which by default was set to 3, but you can edit this to whatever you want. `secretNum` will assign and add one number as a string, this is why this program uses strings and not integers. If this was adding integers, it would increase in value, example, as integers 4 + 3 + 1 would equal 8, but as strings, it makes 431.

```
<pre class="wp-block-code">```
    secretNum = ''
    for i in range(numDigits):
        secretNum += str(numbers[i])
    return secretNum

```
```

Next up, the `getClues` function.

```
<pre class="wp-block-code">```
def getClues(guess, secretNum):
    if guess == secretNum:
        return 'You got it!'
    clues = []

```
```

```
<pre class="wp-block-code">```
for i in range(len(guess)):
        if guess[i] == secretNum[i]:
            clues.append('Fermi')
        elif guess[i] in secretNum:
            clues.append('Pico')
    if len(clues) == 0:
        return 'Bagels'
    else:
        clues.sort()
        return ''.join(clues)
if __name__ == '__main__':
    main()

```
```

## 4. Reflection (WIP)

How defining functions work, still getting my head around flow control, this helped to see a function on later lines can be called on eariler on in the program.

I don’t always need to use `elif`, I’m still getting the hang of `if` statements, so it’s nice to see how you don’t always need to use `elif`.

The question about why numDigits errors when the number is over 10, that’s because there’s only 0 through to 9, there’s only 10 digits to choose from.