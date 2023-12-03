---
id: 4680
title: "Basic Python Project \u2022 Is It Raining?"
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4680
url: "/?p=4680"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Basic-Python-Project--Is-It-Raining-e16j8nq" width="400px"></iframe>Learning python? It’s an incredible programming language to have in your tool belt.

This project is inspired by an early example from [Automate The Boring Stuff with Python](https://automatetheboringstuff.com/2e/).

## 1. Flow Control

This python project is to impliment this flow chart:

<div class="wp-block-image"><figure class="alignleft is-resized">![https://p146.p4.n0.cdn.getcloudapp.com/items/QwuAQJw4/7bd7f883-0412-4c17-be0a-c76bf7f3ed8b.jpeg?v=8bf921ac8a83df1bad0164828c7eca03](https://p146.p4.n0.cdn.getcloudapp.com/items/QwuAQJw4/7bd7f883-0412-4c17-be0a-c76bf7f3ed8b.jpeg?v=8bf921ac8a83df1bad0164828c7eca03)</figure></div>Taken from [chapter 2](https://automatetheboringstuff.com/2e/chapter2/), there’s a few things to digest, see the code step by step in [Python Tutor](http://pythontutor.com/visualize.html#code=outside%20%3D%20False%0Arain%20%3D%200%0Aumbrella%20%3D%200%0Awhile%20outside%20%3D%3D%20False%3A%0A%20%20%20%20while%20%28rain%20!%3D%20'y'%20or%20rain%20!%3D%20'n'%29%3A%0A%20%20%20%20%20%20%20%20rain%20%3D%20input%28'Rain%3F%20y/n%20'%29%0A%20%20%20%20%20%20%20%20break%0A%20%20%20%20if%20rain%20%3D%3D%20'y'%3A%0A%20%20%20%20%20%20%20%20print%28'Get%20an%20umbrella.'%29%0A%20%20%20%20%20%20%20%20while%20%28umbrella%20!%3D%20'y'%20or%20umbrella%20!%3D%20'n'%29%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20umbrella%20%3D%20input%28'Umbrella%3F%20y/n%20'%29%0A%20%20%20%20%20%20%20%20%20%20%20%20break%0A%20%20%20%20%20%20%20%20if%20umbrella%20%3D%3D%20'n'%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20print%28'Wait%20a%20while.'%29%0A%20%20%20%20%20%20%20%20elif%20umbrella%20%3D%3D%20'y'%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20outside%20%3D%20True%0A%20%20%20%20elif%20rain%20%3D%3D%20'n'%3A%0A%20%20%20%20%20%20%20%20outside%20%3D%20True%20%0Aprint%28'Go%20outside.'%29%0Aexit%28%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false).

Let’s write the steps is psuedoe code:

1. Ask if it’s raining?
2. If no, go outside.
3. If yes, ask if there’s an umbrella?
4. If umbrella no, wait and ask if raining again.
5. If umbrella yes, go outside.

## 2. While Loop

Let’s start with the outside variable and it’s while loop.

```
<pre class="wp-block-code">```
outside = False
while outside == False:
		# Other code goes here.
print('Go outside.')
exit()

```
```

As all paths lead to outside, it makes sense for the program to check if the user can go outside or not.

As long as outside is set to False, the user isn’t able to go out. But once other conditions are met and outside is True, then the program ends.

## 3. Input Validation

Let’s make a simple input validation when asking if there’s rain or not. This way the user can’t put in anything but what is expected.

While rain isn’t equal to y or n, continue asking the same question.

```
<pre class="wp-block-code">```
rain = 0
while (rain != 'y' or rain != 'n'):
	rain = input('Rain? y/n ')
        break
if rain == 'y':
	# More code goes here
elif rain == 'n':
	outside = True

```
```

We’ll use this same input validation for our other questions that require user input.

If there is rain, the program will continue asking questions. But if there’s no rain, then outside is set to True and will break the original while loop.

## 4. If Else Statements

Let’s add the last variable, umbrella.

```
<pre class="wp-block-code">```
umbrella = 0
if rain == 'y':
    print('Get an umbrella.')
    while (umbrella != 'y' or umbrella != 'n'):
        umbrella = input('Umbrella? y/n ')
        break
    if umbrella == 'n':
        print('Wait a while.')
    elif umbrella == 'y':
        outside = True
elif rain == 'n':
    outside = True 

```
```

Depending on the users input yes or no, either it will tell them to wait and then go back to the rain question or it will end the main while loop.

## 5. Failed Attempts

Just for a bit of fun, here are two of my failed attempts on the road to figuring out this program.

Version 2:

```
<pre class="wp-block-code">```
rain = input('Is it raining? y/n ')
while rain == 'y':
    print('
    if rain == 'n':
        print('Go outside!')
    else:
        break

```
```

Version 1:

```
<pre class="wp-block-code">```
raining = input('Is it raining? y/n ')
if raining == 'y':
    print('It\\'s raining!')
    umbrella = input('Do you have an umbrella? y/n ')
    if umbrella == 'n':
        print('Wait a while.')
        print('Time passes...')
        raining = input('Is it raining? y/n ')
        if raining == 'y':
            print('Wait a while, again.')
        else:
                print('Go outside.')
    else:
        print('Go outside.')
else:
    print('''It\\'s not raining!
    
    Go outisde!''')

```
```

If you have any feedback, please send me a message via [Twitter](https://twitter.com/mrashleyball).

This is Day 13 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the journey!

Happy Hacking.