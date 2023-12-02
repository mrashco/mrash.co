---
id: 4708
title: Bagels | Beginner Python Project
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4708
url: "/?p=4708"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

Want a beginner Python Project that’s going to test you? A program longer than 40 lines of code?

Look no further, here’s Bagels!

This is from [The Big Book of Small Python Projects](https://inventwithpython.com/bigbookpython/) – [Chapter 1 Bagels](https://inventwithpython.com/bigbookpython/project1.html)

<iframe frameborder="0" height="500px" loading="lazy" src="https://replit.com/@mrashleyball/Bagels?lite=true" width="100%"></iframe>Watch the [Study Session](https://youtu.be/Fg_EoUtCfOU) for the full programming behind the scenes.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/Fg_EoUtCfOU?feature=oembed" title="Bagels • Beginner Python Project • Big Book of Small Python Projects • Study Session #2 (LoFi Chill)" width="800"></iframe></div></figure>## 1. Global Variables and Main Function

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

```
<pre class="wp-block-code">```
while True:
		secretNum = getSecretNum()
		print('I have thought up a number.')
		print(' You have {} guesses to get it.'.format(maxGuesses))

```
```

## 2. Number of Guesses (Coming Soon)

```
<pre class="wp-block-code">```
numGuesses = 1
        while numGuesses <= maxGuesses:
            guess = ''
            while len(guess) != numDigits or not guess.isdecimal():
                print('Guess #{}: '.format(numGuesses))
                guess = input('> ')

            clues = getClues(guess, secretNum)
            print(clues)
            numGuesses += 1

            if guess == secretNum:
                break
            if numGuesses > maxGuesses:
                print('You ran our of guesses.')
                print('The answer was {}.'.format(secretNum))
        print('Do you want to play again? (yes or no)')
        if not (input('> ').lower().startswith('y')):
            break
    print('Thanks for playing!')

```
```

## 3. Secret Number (Coming Soon)

```
<pre class="wp-block-code">```
def getSecretNum():
    numbers = list('0123456789')
    random.shuffle(numbers)

    secretNum = ''
    for i in range(numDigits):
        secretNum += str(numbers[i])
    return secretNum

```
```

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

## 4. Reflection (Coming Soon)