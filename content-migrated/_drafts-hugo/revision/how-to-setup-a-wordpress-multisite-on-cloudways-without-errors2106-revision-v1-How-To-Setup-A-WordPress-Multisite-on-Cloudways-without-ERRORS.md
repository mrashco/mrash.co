---
id: 4801
title: How To Setup A WordPress Multisite on Cloudways without ERRORS!
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4801
url: "/?p=4801"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/How-To-Setup-A-WordPress-Multisite-On-Cloudways-Without-ERRORS-e16k2a6" width="400px"></iframe>So you want to setup a WordPress Multisite? Well, the good news is I just did that very thing, had a few problems along the way and am going to make your life easier!

## What is WordPress Multisite?

A WordPress Multisite is like a tree of websites branching out. You have the trunk which is the main site, then the branches that stem from the main site are smaller sites. [Read more here.](https://wordpress.org/support/article/multisite-network-administration/)

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-1024x602.png)</figure>## 1. Getting Started

Login to your Cloudways account and add a new application.

<figure class="wp-block-embed is-type-photo is-provider-created-with-cloudapp"><div class="wp-block-embed__wrapper">[![Image 2020-06-21 at 8.51.48 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/4gujOqNX/Image%202020-06-21%20at%208.51.48%20AM.png)](https://a.cl.ly/4gujOqNX)</div></figure>Select your server and then WordPress Multisite option and let that run for a few minutes

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-1-1024x521.png)</figure>## 2. Setup Your Domain

Either you multisite will have a root domain or a subdomain, whatever you want to do. In my case, I want my multisite to be a sub-domain of my main website.

Go to your DNS Management tool, in this case we’re using CloudFlare

Add an ‘A Record’, enter your desired subdomain then the destination of the server for your website.

<figure class="wp-block-image">![Image 2020-06-21 at 9.03.08 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/qGuKlWBl/Image%202020-06-21%20at%209.03.08%20AM.png?v=d55fb887d44e04a7d6adf5f8c139a5cc)</figure>Then go back to Cloudways when your WordPress multisite has installed and find the Domain Management section.

<figure class="wp-block-image">![Image 2020-06-21 at 9.05.25 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/wbuWK4BR/Image%202020-06-21%20at%209.05.25%20AM.png?v=141446b12cc0f321b251ec404b6be954)</figure>## 3. Setup Multisite in WordPress

Now you can log in to your new Multisite, you’ll notice at the moment, it looks like any regular installation of WordPress, and that’s because it is. We just need to edit two files in order to access WordPress’ Multisite capabilities.

Deactivate all plugins on the new site, they may cause conflictions so better just get them out of the way.

<figure class="wp-block-image">![Image 2020-06-21 at 9.11.12 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/jkuQYG0Q/Image%202020-06-21%20at%209.11.12%20AM.png?v=3aace96a06979e0411f60cd4d9188598)</figure>Then go to Tools &gt; Network Setup

Here we need to choose how we want our multisite to display and function. There are differences for both and benefits, do some research if you’re unsure. For me, I don’t want my subdomain changing, I want that static, so I’m selecting the ‘Sub-directories’ option.

<figure class="wp-block-image">![Image 2020-06-21 at 9.12.49 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/z8u84jRb/Image%202020-06-21%20at%209.12.49%20AM.png?v=83d192baeb987688c20de9a3bc93f107)</figure>Then hit install down the bottom

## 4. Editing Files via SFTP &amp; VS Code

Now we need to copy &amp; paste some code into two separate files via the Secure File Transfer Protocol. If you’re familiar with this process then great! You may already be using FileZilla or another program. If you’re not, let me walk you through it using Visual Studio Code, it’s easy and makes changing code a breeze!

Download [Visual Studio Code](https://code.visualstudio.com/) &amp; install it on your machine

Then go to Extensions &gt; Search Bar &gt; FTP-Simple &amp; install this extension

<figure class="wp-block-image">![Image 2020-06-21 at 9.20.52 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/NQugK0mP/Image%202020-06-21%20at%209.20.52%20AM.png?v=ee05180b7821c5cba5cdb84d0aa96003)</figure>Then press F1 &gt; and type ‘ftp-simple: Config – FTP connection setting’

<figure class="wp-block-image">![Image 2020-06-21 at 9.26.08 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/wbuWK4pQ/Image%202020-06-21%20at%209.26.08%20AM.png?v=43d6b4aee2fadbb1bd11f1f336982006)</figure>Use the follow code to assist you with inputting your SFTP credentials

```
<pre class="wp-block-code">```
	{
		"name": "Name Server Here",
		"host": "Server IP Address Here",
		"port": 22,
		"type": "sftp",
		"username": "Username Goes Here",
		"password": "Password Goes Here",
		"path": "/",
		"autosave": true,
		"confirm": false
	}
```
```

Now if you have those details already, great! Put them in. If not, lets go back to Cloudways and grab them.

Go to Server &gt; Select Server &gt; Master Credentials

<figure class="wp-block-image">![Image 2020-06-21 at 9.29.25 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/X6uo9JAr/Image%202020-06-21%20at%209.29.25%20AM.png?v=8d6bb3c4688d922750ef5fb4f9743fae)</figure>Cloudways makes it super easy to just click and copy, so use each detail here and put them back into Visual Studio Code to now enable STFP to your server.

Once you’ve done that, close the config file and we’re going to connect! Press F1 &gt; and type ‘ftp-simple: Remote directory open to workspace’

Now you can select your server and destination. Select Server &gt; Applications &gt; Name Of Your App &gt; public\_html &gt; Current Directory

Now we want to select and make backups of our two files. The .htaccess file &amp; wp-config.php file. SImply select, right click, copy and then CTRL + V to paste it.

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-7-1024x576.png)</figure> Make sure you open your terminal by going to the top bar &gt; Terminal &gt; New Terminal &amp; in the Output tab, change the dropdown to ftp-simple.

Now copy over your code from your WordPress site to your wp-config.php file

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-5-1024x576.png)</figure>Then copy your .htaccess code in between the &lt;IfModule&gt; tags.

<figure class="wp-block-image">![Image 2020-06-21 at 9.41.01 AM](https://p144.p3.n0.cdn.getcloudapp.com/items/jkuQYGxB/Image%202020-06-21%20at%209.41.01%20AM.png?v=20e9986848dbd68da8a7c01b2cb5693c)</figure>After that, go back to WordPress resresh page and log back in. It all SHOULD be fine, but it wasn’t for me.

## 5. Permissions Errors via SFTP 

Now if it’s all working for you, great! But this is where I had problems, took me a bit to figure out, but there terminal in Visual Studio Code is a lifesaver!

I was receiving permission denied errors, so I didn’t have the correct access to upload back to my server. So if you have this issue, let’s fix it!

First, you need your Public Ip Address. So go to [What’s My Ip](https://www.whatismyip.com/what-is-my-public-ip-address/) and copy it from there.

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-4-1024x522.png)</figure>Then we’re going to add it to the server whitelist so you have permission

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-3-1024x521.png)</figure>Lastly, you want to reset your file permission to make sure it’s working. If you have any troubles, see the [Cloudways Support article here.](https://support.cloudways.com/whitelist-ips-for-ssh-sftp/)

Go to Your Application &gt; Application Settings &gt; Reset File / Folder Permissions and hit the refresh icon

If you need any help with this, see [Cloudways Support](https://support.cloudways.com/reset-file-and-folder-permissions-of-an-application/)

<figure class="wp-block-image size-large">![](https://mrash.co/wp-content/uploads/2020/06/image-2-1024x521.png)</figure>## 6. Finishing Up

Now you can upload files at will, edit code or whatever on your new WordPress multisite, congrats! If you need any more assistance, see [Cloudways Support article on WordPress multisites. ](https://support.cloudways.com/how-to-setup-a-wordpress-multisite-on-cloudways/)

If you found this article helpful please consider supporting me by purchasing via my [affiliate link here.](http://links.mrash.co/cloudways)