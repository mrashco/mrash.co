---
id: 4699
title: WordPress App Won&#8217;t Connect To Website &#8211; Cloudways Self-hosted
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4699
url: "/?p=4699"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/WordPress-App-Wont-Connect-To-Website--Cloudways-Self-Hosted-e16j80r" width="400px"></iframe>Your [WordPress](https://play.google.com/store/apps/details?id=org.wordpress.android) app won’t connect to your website? Let’s fix that!

Note, this is for Cloudways self-hosted websites.

Follow [this guide](https://apps.wordpress.com/mobile-app-support/my-sites/how-do-i-connect-my-site/) if you need help setting up the app and connecting it to your website.

## 1. Check Jetpack Is Installed

Make sure you have the most up-to-date plugin [Jetpack](https://wordpress.org/plugins/jetpack/). It’s what connects your self-hosted site to the app.

If you’ve never set Jetpack up, follow [this guide](https://www.cloudways.com/blog/wordpress-jetpack-plugin/) to help you.

## 2. Define Error

The reason it’s not working might be a couple of things, welcome to troubleshooting i.e. try stuff until you fix it.

Start with [Fixing Jetpack Connection Issues](https://jetpack.com/support/getting-started-with-jetpack/fixing-jetpack-connection-issues/), as it’s most likely either:

1. Reinstall Jetpack;
2. plugin conflict or;
3. [XML-RPC](https://apps.wordpress.com/mobile-app-support/my-sites/inaccessible-xml-rpc-connection-error/).

To get a better idea of what it could be, use [Jetpacks Debug Tool](https://jptools.wordpress.com/debug/) to find out. Read more about the [possible issues](https://apps.wordpress.com/mobile-app-support/login-signup/i-cant-connect-to-my-self-hosted-site-what-should-i-do/) to get a better insight.

## 3. Resolve Issue

If it’s a plugin conflict, disable all plugins bar Jetpack and test connection.

If XML-RPC, you may get this message “Inaccessible XML-RPC Connection error”.

This is disabled by default on Cloudways systems, so it’s a simple enable fix.

XML-RPC allows “you to build remote connections between your WordPress site and external applications.”

Go to Cloudways &gt; Application &gt; Application Settings &gt; Enable.

For more assistance, see [Disable XML-RPC in WordPress Applications](https://support.cloudways.com/en/articles/5127178-disable-xmlrpc-in-wordpress-applicationsFor).