---
id: 4759
title: Python Range Function | Quick Python Project Lesson
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4759
url: "/?p=4759"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
---

So you’re learning Python and want to understand the range function, welcome!

The range function paired with a for loop is a great way to repeat code a number of times.

Let’s learn the basics of the range function with Python and then it’s over to you for a little project.

## 1. Basics

Let’s have a simple counter go from 1 to 5, and show the results as it counts.

It would look like this:

```
<pre class="wp-block-code">```
for i in range(5):
    print('Count: ' + i)

```
```

Remember, in this case, `i` doesn’t have any other value or purpose than just a counter variable.

Try that. Oh wait, we forgot to convert the integer `i` into a string data type, remember, Python can’t concatenate different data types together.

So add a string conversion function around the `i` variable and it looks like this:

```
<pre class="wp-block-code">```
for i in range(5):
    print('Count: ' + str(i))

```
```

Ah, much better, the output shows:

```
<pre class="wp-block-code">```
Count: 0
Count: 1
Count: 2
Count: 3
Count: 4

```
```

Great, let’s just stick with range for a while and learn about the parameters this function has.

Range when passed a single integer like 5, simply counts up until but not including 5. That’s why Python starts at 0 and ends at 4, it’s still 5 counts. But what if we wanted it to start actually at digit 1 and go to digit 5?

```
<pre class="wp-block-code">```
for i in range(1,5):
    print('Count: ' + str(i))

```
```

Now this won’t work as Python counts up to but not including, so we’ll get the output of:

```
<pre class="wp-block-code">```
Count: 1
Count: 2
Count: 3
Count: 4

```
```

Change the range from 5 to 6 and now we’ll get the correct output from 1 to 5.

To explain, we’re changing the parameters of the range function, `range(a,b,c)` . There are three parameters,

1. starting number,
2. ending number,
3. stepping number.

Let’s try and count to 100 in 2’s, 5’s and 10’s, let’s see what that looks like:

```
<pre class="wp-block-code">```
for i in range(1,100,2):
    print('Count: ' + str(i))

```
```

That looks good, right? Starting at 1, going to 100, stepping every 2 integers? Almost, remember how Python works? It counts up to but not including, plus we want it to start at 0 this time. Let’s make that change:

```
<pre class="wp-block-code">```
for i in range(0,102,2):
    print('Count: ' + str(i))

```
```

Okay, what about counting in 5’s to 100?

```
<pre class="wp-block-code">```
for i in range(0,105,5):
    print('Count: ' + str(i))

```
```

And 10’s?

```
<pre class="wp-block-code">```
for i in range(0,110,10):
    print('Count: ' + str(i))

```
```

Great, by now you should have a bit better understanding of the range function and its parameters.

## 2. Projects

### 2.1 Horizontal Pyramid

Here’s a bit of a mission for you to complete, if you choose to do so. Using the range function, build a horizontal pyramid of pound symbols `#`. The output of your program should look like this:

```
<pre class="wp-block-code">```
#
##
###
####
#####
####
###
##
#

```
```

Be aware there are many ways to complete this program, so if you use one, some or none of these, that’s okay, programming is about creativity:

- `range()`
- `print()`
- `variables`

### 2.2 Horizontal Pyramids Forever

Now, for the next challenge, try and build a horizontal pyramid that grows and shrinks forever, as in, repeatedly. What you’ll need (use one, some or none):

- `while loop`
- `range()`
- `print()`
- `variables`
- `time module`

Here’s what it would look like, but the goal is for it to repeat, so this would go on forever until the user uses `CTRL + C` to interrupt and quit the program.

```
<pre class="wp-block-code">```
#
##
###
####
#####
####
###
##
#

#
##
###
####
#####
####
###
##
#

```
```

### 2.3 User Horizontal Pyramid

The last project, it’s more like a minor tweak or update to be fair.

Let the user select the size of the pyramid, so if the user wants it to be small, they enter 3 or 4, but if they want it to be massive, they can enter 80 or whatever they like.

## 3. Answers

If you don’t want to cheat, look away now, scroll up! I’m warning you… okay, continue, you may pass. Here’s the program for the first, basic project.

```
<pre class="wp-block-code">```
x = 0
for i in range(5):
    print('#'*x)
    x += 1
for i in range(5):
    print('#'*x)
    x -= 1

```
```

To explain the horizontal pyramid program, we’ve set `x` to 0 and we’re repeating the `#` times by `x`, in the beginning, it’s 0, but every time it’s increased by 1 by `x += 1` now `+=` is a nice little shorthand where you can both plus and assign in Python.

After increasing in value five times, then the program goes in reverse and decreases five times to create the final product. Nice work!

Let’s take a look at the next project.

```
<pre class="wp-block-code">```
import time

x = 0

while True:
    for i in range(x, 6):
        print('#'*x)
        x += 1
        time.sleep(0.1)
    for i in range(x):
        print('#'*x)
        x -= 1
        time.sleep(0.1)

```
```

First up we’re importing the time module to give the program a visual aid for the user, try it without the `time.sleep(0.1)` and you’ll understand why it’s important.

Then declaring `x` as 0 before the `while` loop, this is how we can create the repeating behaviour of the program. There are two `range` functions, one increasing the value of `x` and one decreasing. We’re repeating each `range` function based on `x` the first as the starting number, and then the second as the default.

And the last edit of the project, let’s see what that looks like.

```
<pre class="wp-block-code">```
import time

x = 0
y = int(input('Enter a number: '))

while True:
    for i in range(x, y):
        print('#'*x)
        x += 1
        time.sleep(0.1)
    for i in range(x):
        print('#'*x)
        x -= 1
        time.sleep(0.1)

```
```

Now, not a big change here, just adding another variable, this time `y` is assigned to the user’s input. Then updating the first `range` function with the end number parameter to be the new variable, that’s it!

It’s a simple, fun little project to see in action, hope you enjoy it! For more reading, see the [python.org docs](https://docs.python.org/3.10/library/stdtypes.html?highlight=range#range).

## 4. Reflection

This was a lot of fun to write up and share, I love creating mini-lessons like this for learners out on the interwebs. In fact, this program has a bit of a history with me, I attempted Harvard’s CS50X 2019 course and failed spectacularly.

I’m not sure if they still have the same assessment, but the goal was to construct pyramids for Mario, yeah that Mario, to jump over like a platform game. I failed! Like, I had no idea what I was doing, and I didn’t persist through so I just gave up.

It’s nice, fast forward a year or so, I’m back into learning programming and this time around Python is SO much better to start off with. I’d love to see intro courses start with Python over other languages.

I hope you enjoyed the lesson and I’ll see you in the next one!

This is Day 29 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to the [newsletter](https://go.mrash.co/newsletter) for updates and if you have feedback, message me via [Twitter](https://twitter.com/mrashleyball). Happy Hacking.