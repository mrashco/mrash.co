---
title: Replit EdFest 2022 Jam - Intro To PyScript
author: Mr Ash
type: "post"
published: 2022-07-28
lastUpdated: 2022-11-05
url: "/replit-edfest-2022-jam-intro-to-pyscript/"
categories: Programming
tags:
  - PyScript
  - Python
  - Replit
---

ATTENTION! If you’d like to do the course yourself, [join up using this link for FREE](https://replit.com/teams/join/mpanteneugnunwnbahvbvtxmxtomkcdd-it38).

And don’t forget to watch the video walkthrough.


Welcome to your Intro to PyScript, a simple replit that teaches you the basics of the modern Python web dev technology. You’re going to set up your own simple HTML page with a linked Python program. You’ll enable PyScript, take user data, run it through your program and print it back out to the user.

You’re learning the basics of building front-end, browser-based web applications. With minimal setup, it’s all about your imaginations limitation. Follow the steps below to complete the project, enjoy and we hope you learn a lot!

**Goals**

1. HTML page w/ Bulma CSS Framework
2. Use PyScript to create a Python program
3. Produce a complete, simple web app

## HTML page w/ Bulma CSS Framework

### HTML Structure

Okay, let’s start with a basic `html` structured page, and save it in `index.html`.

```html
<html>
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
		...
  </body>
</html>
```

### CSS + Meta Links

Great, next we’ll be using some `css` files over the air via a CDN (Content Distribution Network). Make sure to include these in-between `<head></head>` tags.

```html
<link rel="stylesheet" href="<https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css>">
<link rel="stylesheet" href="<https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.2/css/all.min.css>"/>
```

While we’re adding links, let’s take a look at what’s going to help out later, [PyScript](https://pyscript.net/). Currently, it shows the following links, but bare in mind these will change in the future so check their website.

```html
<link rel="stylesheet" href="<https://pyscript.net/alpha/pyscript.css>"/>
<script defer src="<https://pyscript.net/alpha/pyscript.js>"></script>
```

<!-- <div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> -->

### Complete Layout

Awesome, now it’s time to set up the full page structure, from here on out the `html` code will be in shorthand for you to write yourself. Keep in mind this all goes within the `<body></body>` tags. Here’s the `html` outline for you to create, notice the indention.

Note, `.` (dots) are classes, `#` (hashtags) are IDs, for example `section.container` would be `<section class="container"></section>` and `label#name` would be `<label id="name"></label>`. If you’ve used [Emmet](https://emmet.io/), this will be familiar. If not, don’t worry, you can pick it up as you go.

```html
section.container
  section.notification
    h1.title
    label
    input#name.textarea
    label
    input#email.textarea
    button#convert.button
  section.notification
    div#output
pyscript
```

To explain, you’re setting up a primary section with two sub-sections. The first section will have the titles, labels and inputs. And the second section will display the outputs after PyScript has had it’s fun.

## Use PyScript to create a Python program

Alright, now we’re getting into the weeds… I mean, fun stuff, because it is a lot of fun. The links we added in earlier are going to allow us to use Python in the browser, how cool? Yep, just HTML and Python, crazy!

### The PyScript HTML Tag

Let’s start by adding the PyScipt specific syntax to see it in action and get a taste for it all. Under your `<button></button>` tags inside `index.html`, add `<py-script></py-script>`. This is one of a few new PyScript syntaxes brought into HTML. Inside the tags, write `print('Hello world')` the infamous right of passage in coding. Run your code and walla, you have Python in the browser, easy hey?

Now switch over to `main.py` and link to `index.html`. Copy `print('Hello world')` statement from your code and paste it into `main.py`. Update your PyScript tag to look like this `<py-script src="main.py"></py-script>`. If you run the code again you shouldn’t see any changes, ‘Hello World’ should be printing as normal, but the difference this time is it’s now a separate Python file, great work.

Before moving on, add a new tag to your button `<button pys-OnClick="convert"></button>`, this calls the function we’ll set up in `main.py`. Okay, let’s focus on building out our `main.py` program and seeing more of what PyScript can do.

### PyScript’s Elements() Class

Alright, now in `main.py` it’s time to set your objects, this is going to allow PyScript to manipulate HTML elements. We do this by calling `Elements('Element-ID')` class, where `'Element-ID'` is for example `name` in `id="name"` and assigning it to a variable. For example, here’s how to create an object for the first input in `index.html`.

```html
input_name = Element('name')
```

Go ahead and repeat this for `email` and `output`.

Remember, an object is an instance of a class, and a class has it’s own methods, i.e. functions designed for class objects. Let’s take a quick look at some other methods. If we run `dir(input_name)` we can see all the methods associated with the class, let’s print a few out.

```html
print(input_name.id)
print(input_name.element)
print(input_name.value)
```

Feel free to remove these print examples or highlight them and press `CTRL/CMD + /` to comment them out.

## Produce a complete, simple web app

Okay, now you’ve got a better idea of what’s going on, let’s build out the `main.py` more.

The goal here is to take the user’s input from the input fields in `index.html`, let PyScript manipulate them and then display it back to the user.

### Code Check

Let’s check our code before we go any further, here’s `index.html`.

```html
...
  <body>
    <section class="container">
      <section class="notification">
        <h1 class="title">Title</h1>
        <label for="name">Name</label>
        <input id="name" class="textarea">
        <label for="email">Email</label>
        <input id="email" class="textarea">
        <button class="button" id="convert" pys-onClick="convert">Convert</button>
      </section>
      <section class="notification">
        <div id="#output"></div>
      </section>
    </section>
    <py-script src="main.py"></py-script>
  </body>
</html>
```

And here’s `main.py` so far.

```python
input_name = Element('name')
input_email = Element('email')
output_area = Element('output')
```

### Main.py Function

Great work, so our button in `index.html` has an attribute of `pys-onClick="convert"` which invokes a Python function called convert. Let’s code the convert function now.

```python
def convert(*args, **kwargs):
  pass
```

Currently, the convert function simply passes without doing anything else, it’s up to you to write this code. Implement an f string that writes to the `output_area`. Now to do this, there’s a write method, that’s convenient. Use `output_area.write()`, don’t forget to include `input_name.value` and `input_email.value` which uses the inputs values.

If you’re stuck, write an f string like this `f'Hello, my name is {name}, and my email is {email}` but using the methods listed above.

Awesome, now it’s the moment of truth, run your code and see what you’ve got!

<!-- <div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> -->
 
 ### Publish and Share

If all goes well, you’ll have your first PyScript application running on HTML &amp; Python, cool!

Now it’s time to tell the world, tweet [@mrashleyball](https://twitter.com/mrashleyball) and [@pyscript\_dev](https://twitter.com/pyscript_dev) – we’d love to hear!

If you’d like to see my own implementation, here’s [Mailto Me](https://mrashleyball.github.io/mailto-me/). A simple way to generate HTML mailto links with embedded subject lines &amp; body messages. Feel free to use it to help you with your project.

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/74xkQeObO0Y?feature=oembed" title="Intro To PyScript (Replit EdFest 2022)" width="800"></iframe></div></figure> -->

{{<youtube 74xkQeObO0Y>}}

If you’d like to contact me, feel free to reach out over Twitter. Feel free to check out my blog [mrash.co](https://mrash.co/) for regular articles on Cyber Security, Python Programming and Work-Life. I also have a [monthly newsletter](https://mrash.co/newsletters/) to keep in touch.

Thanks for reading!