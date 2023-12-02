---
id: 4566
title: "Optimize WordPress Speed \u2022 How To Load WordPress Fast"
author: Mr Ash
type: "post"
guid: https://mrash.co/?p=4566
url: "/optimize-wordpress-speed-how-to-load-wordpress-fast/"
primary_accent:
- '#004CFF'
secondary_accent:
- '#FF9D00'
ekit_post_views_count:
- '474'
image: https://images.unsplash.com/photo-1498084393753-b411b2d26b34?ixid=MnwxNTI0MzJ8MHwxfGFsbHx8fHx8fHx8fDE2MzI3MTM3NDI&ixlib=rb-1.2.1&fm=jpg&q=85&fit=crop&w=2560&h=1440
categories: "['WordPress']"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Optimize-WordPress-Speed--How-To-Load-WordPress-Fast-e17us1l" width="400px"></iframe>Are you obsessed with website speeds?

Designing a beautiful WordPress website is one thing, but to make it load fast, that’s another.

After years of building client sites and perfecting the speed formula, I’m finally sharing the secret.

Spoiler, there’s no secret, it’s a simple trial and error thing, feel free to copy this exactly or use it as a blueprint for you to work from.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/xQu62AKq/a76df9a9-82d5-404c-b9d8-8bc6cef6bd73.jpeg?v=05d384f238b319fd83944d605bff158c](https://p146.p4.n0.cdn.getcloudapp.com/items/xQu62AKq/a76df9a9-82d5-404c-b9d8-8bc6cef6bd73.jpeg?v=05d384f238b319fd83944d605bff158c)</figure>See the live report via [GTMetrix](https://gtmetrix.com/reports/mrash.co/Ors42m20/).

*Disclaimer, this is not a step by step guide. If you need help setting up your website, see [How To Setup Your Own Website](https://mrash.co/how-to-setup-your-own-website-a-complete-guide-to-hosting-a-wordpress-website/). Before making any changes, make sure you have a backup of your website and are in a development environment to ensure you do not break anything.*

## 0. Mindset

Before we get into the nitty-gritty, let’s just talk broadly. **Only have what you need on your website.** Don’t upload countless images, plugins or themes just for the sake of it.

## 1. Hosting – Cloudways

Easily the most important aspect of website speed is the computer, or server which stores the web files. This is your web host, there’s good web hosting companies out there. However, I recommend [Cloudways](https://go.mrash.co/cloudways).

Specifically, the [Cloudways](https://go.mrash.co/cloudways) Vultr High Frequency web servers. If interested, see [my comparison](https://mrash.co/standard-vs-high-frequency-cloudways-vultr-comparison/) on why this is a good option.

So, you’re using Cloudways? Great! Now how do you configure the server? Let’s take a look.

Here’s the Managing Services:

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/P8uGoy00/82312f05-266f-4cc7-b8b0-a882a144c4ab.jpeg?v=622aade8249e10f47ae905354e6739d1](https://p146.p4.n0.cdn.getcloudapp.com/items/P8uGoy00/82312f05-266f-4cc7-b8b0-a882a144c4ab.jpeg?v=622aade8249e10f47ae905354e6739d1)</figure>Go to Settings &amp; Packages, Basic. Make sure to increase the Memory Limit.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/4gulqlqK/544b49e0-bc9e-42a3-bcef-2fdd7f205ca4.jpeg?v=85f66d493b648ea2948b5873e7d48318](https://p146.p4.n0.cdn.getcloudapp.com/items/4gulqlqK/544b49e0-bc9e-42a3-bcef-2fdd7f205ca4.jpeg?v=85f66d493b648ea2948b5873e7d48318)</figure>Now go to Advanced, PHP.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/v1u070pl/7d18967e-2dce-477b-a364-2096993e7df4.jpeg?v=5c48b88e8c16bb684a566414df6fc96a](https://p146.p4.n0.cdn.getcloudapp.com/items/v1u070pl/7d18967e-2dce-477b-a364-2096993e7df4.jpeg?v=5c48b88e8c16bb684a566414df6fc96a)</figure>While still in Advanced, scroll to MySQL, NGINX and Varnish. Add Cloudflare to the WAF Module, this will come in handy soon.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/rRubYbeG/40ec0e73-be64-4341-9d11-3042e3ec6ea4.jpeg?v=a28222d5764d884c998a07f2e9ffd5eb](https://p146.p4.n0.cdn.getcloudapp.com/items/rRubYbeG/40ec0e73-be64-4341-9d11-3042e3ec6ea4.jpeg?v=a28222d5764d884c998a07f2e9ffd5eb)</figure><figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/geuAGANL/705ef90e-34bc-4279-9540-ee79c0187fad.jpeg?v=657692293ef95b6077c5d7f9dc29430f](https://p146.p4.n0.cdn.getcloudapp.com/items/geuAGANL/705ef90e-34bc-4279-9540-ee79c0187fad.jpeg?v=657692293ef95b6077c5d7f9dc29430f)</figure>Now go over to Packages and update PHP and MySQL. It’s always a good idea to run the latest, stable version of these coding languages for your websites.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/KouJX7my/d5ecf630-4b50-4c43-954d-9d123c3596a5.jpeg?v=951abdf3a29094622f74d2a920e8f27a](https://p146.p4.n0.cdn.getcloudapp.com/items/KouJX7my/d5ecf630-4b50-4c43-954d-9d123c3596a5.jpeg?v=951abdf3a29094622f74d2a920e8f27a)</figure>## 2. Content Delivery – Cloudflare

Let’s add an amazing connection layer to your website in the form of a Content Delivery Network (CDN) via Cloudflare. It’s an amazing service that won’t cost you anything, yes, it’s free and adds a level of privacy and security to your website.

If you’re not using Cloudflare, it’s as simple as creating an account, adding your domain and updating your name servers via your domain host. If that didn’t make sense, see [How to Use Cloudflare CDN on Cloudways](https://support.cloudways.com/en/articles/5133527-how-to-use-cloudflare-cdn-on-cloudways).

Go to Speed, Auto Minify and Brotli, tick the following boxes.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/z8urj1XD/016a79de-268b-4012-a5b6-cd06387338cc.jpeg?v=a815c3b936400f99e7b35d7103d7902b](https://p146.p4.n0.cdn.getcloudapp.com/items/z8urj1XD/016a79de-268b-4012-a5b6-cd06387338cc.jpeg?v=a815c3b936400f99e7b35d7103d7902b)</figure>Then, go to Rules, Page Rules and apply the following 3 rules.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/7KuEGAR5/0b86c929-01ce-4e88-8801-721f44e3bc3f.jpeg?v=ca5820f5ada6efb97f6701e13847fe4c](https://p146.p4.n0.cdn.getcloudapp.com/items/7KuEGAR5/0b86c929-01ce-4e88-8801-721f44e3bc3f.jpeg?v=ca5820f5ada6efb97f6701e13847fe4c)</figure>It’s a good idea to purge the cache after making these changes.

For a deeper dive into Cloudflare, see [Caching WordPress Pages using Cloudflare Page Rules](https://wpspeedmatters.com/caching-html-pages-at-the-edge-using-cloudflare/).

## 3. WordPress – Plugins and Themes

WordPress alone is actually good at its speed, the community of contributes and developers who build and make WordPress are always improving it.

It’s a good idea to update to the latest version of WordPress.

For your WordPress theme, there’s a lot of options, I recommend [Astra](https://go.mrash.co/astra), [OceanWP](https://go.mrash.co/oceanwp) or [GeneratePress](https://go.mrash.co/generatepress). If you’re building a pure Elementor WordPress website (which I do), use Hello by Elementor.

### WordPress Caching – Breeze

There’s a lot of plugins that achieve this, I’ve tried most of them, I keep coming back to [Breeze by Cloudways](https://wordpress.org/plugins/breeze/). It’s a free, simple (yet powerful) and user-friendly WordPress Caching Plugin developed by the Cloudways team.

When editing each section of Breeze, make sure to select Save Changes as you go.

Go to Settings, Breeze, Basic Options. Tick the following options, Cache System, Minification, Gzip Compression and Browser Cache.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/L1urAeQ8/7b0246b8-2a2d-4ead-8683-c32c0d67a268.jpeg?v=1b339899e6fcd03ae816c654a192faf4](https://p146.p4.n0.cdn.getcloudapp.com/items/L1urAeQ8/7b0246b8-2a2d-4ead-8683-c32c0d67a268.jpeg?v=1b339899e6fcd03ae816c654a192faf4)</figure>Now go to Advanced Options and check Lazy-load images and Group Files for CSS and JS.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/YEuO2PXz/052f7b15-d3ee-4a6c-b5f5-ef3b02a5f46b.jpeg?v=2808c543a5bc48cd0b8e76f03fb342af](https://p146.p4.n0.cdn.getcloudapp.com/items/YEuO2PXz/052f7b15-d3ee-4a6c-b5f5-ef3b02a5f46b.jpeg?v=2808c543a5bc48cd0b8e76f03fb342af)</figure>Then go to the CDN tab and select the Activate CDN option.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/NQuY07oq/eee50db9-e3da-497f-bb1a-0636147d0018.jpeg?v=8079b206e9875be864546d95f95d0528](https://p146.p4.n0.cdn.getcloudapp.com/items/NQuY07oq/eee50db9-e3da-497f-bb1a-0636147d0018.jpeg?v=8079b206e9875be864546d95f95d0528)</figure>Lastly, go to Varnish and select the Auto Purge Varnish option.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/GGupg4WJ/96949fa4-e878-4717-97bf-afd58a51f683.jpeg?v=ff504f3b28e7c1c72ae02e32d2805ad4](https://p146.p4.n0.cdn.getcloudapp.com/items/GGupg4WJ/96949fa4-e878-4717-97bf-afd58a51f683.jpeg?v=ff504f3b28e7c1c72ae02e32d2805ad4)</figure>### WordPress CDN – Cloudflare

Now you’ve already set up Cloudflare, you don’t need to do that again. But there’s a [Cloudflare Plugin](https://wordpress.org/plugins/cloudflare/) developed by the Cloudflare team built for WordPress. See their [Installation section](https://wordpress.org/plugins/cloudflare/#installation) for how to set this plugin up on your website.

To configure this plugin, go to Settings, Cloudflare, Settings and tick Always Online and Auto Purge Content On Update.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Apu9bEx6/f197436e-41b5-4408-b931-aa65366288d0.jpeg?v=6a023d729654a4dbff23aedcd2818dec](https://p146.p4.n0.cdn.getcloudapp.com/items/Apu9bEx6/f197436e-41b5-4408-b931-aa65366288d0.jpeg?v=6a023d729654a4dbff23aedcd2818dec)</figure>### WordPress Images – ShortPixel

There are some good options out there, I like [ShortPixel](https://go.mrash.co/shortpixel), a freemium, easy to use, comprehensive, stable and frequently updated image compression plugin. See their [Installation guide](https://wordpress.org/plugins/shortpixel-image-optimiser/#installation) for more details on setup.

It’s a good idea to manually compress images before you upload to WordPress and let ShortPixel do the rest.

Go to Settings, ShortPixel, General and apply the following settings.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/NQuY07jA/9863fc80-84c4-4fe7-8313-f5712c654502.jpeg?v=fd6bd17ded1f9d49d389552d7af83afa](https://p146.p4.n0.cdn.getcloudapp.com/items/NQuY07jA/9863fc80-84c4-4fe7-8313-f5712c654502.jpeg?v=fd6bd17ded1f9d49d389552d7af83afa)</figure>Then, go to Cloudflare API and add settings there.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/KouJX7nG/6d7f8c00-d1f3-4892-ba53-f3074d121515.jpeg?v=fa26a1cd3249af41454c5ecdbd27f24c](https://p146.p4.n0.cdn.getcloudapp.com/items/KouJX7nG/6d7f8c00-d1f3-4892-ba53-f3074d121515.jpeg?v=fa26a1cd3249af41454c5ecdbd27f24c)</figure>ShortPixel is awesome, just for fun, here’s how much bandwidth I’ve saved while using it.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/Apu9bEel/bc0166b1-2f78-492b-9a3a-570e98202662.jpeg?v=3e988735c24c09cd997ae6861555232c](https://p146.p4.n0.cdn.getcloudapp.com/items/Apu9bEel/bc0166b1-2f78-492b-9a3a-570e98202662.jpeg?v=3e988735c24c09cd997ae6861555232c)</figure>