---
id: 4798
title: Standard vs High Frequency &#8211; Cloudways Vultr Comparison
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=4798
url: "/?p=4798"
---

<iframe frameborder="0" height="102px" loading="lazy" scrolling="no" src="https://anchor.fm/mrashleyball/embed/episodes/Standard-Vs-High-Frequency--Cloudways-Vultr-Comparison-e16l43i" width="400px"></iframe><figure class="wp-block-embed aligncenter is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/Edyu-KS0On0?feature=oembed" title="Standard vs High Frequency - A Cloudways Vultr Comparison | WordPress Speed Test | #cloudways #wp" width="800"></iframe></div></figure>So you’re thinking of changing to the new High-Frequency servers from Vultr that Cloudways [has just released](https://www.cloudways.com/blog/introducing-vultr-high-frequency-compute-servers/)? Or at the very least you’re interested in how they perform, me too.

I thought I’d conduct a little experiment to see the results for myself, a classic head to head competition style situation.

Cloudways is an incredible platform for hosting websites and their Vultr options have been a personal favourite of mine for years.

<iframe allowfullscreen="true" frameborder="0" height="569" loading="lazy" mozallowfullscreen="true" src="https://docs.google.com/presentation/d/e/2PACX-1vT-euOg0j3dA7EGq8_8en9YlpBiOoAq9LNl7EeWbbJHl5v_wVFpP6trzYB3W4dZAOLpYBPvRbahK3ga/embed?start=false&loop=false&delayms=3000" webkitallowfullscreen="true" width="960"></iframe>## Setup

For this test, I’m comparing Vultr’s Standard Server to their High-Frequency Server available on Cloudways. Both are located in the Pacific option in Sydney.

I’ve installed a clean version of WordPress on each server and have recorded three versions to see how each server performs in different states of a website.

1. Base – which is pure vanilla install, no added plugins, themes or files.
2. Basic – installed 10 plugins and one theme, no other changes.
3. Multi – added multiple pages, images, plugins and themes.

Tool used for server testing is Pingdom Tools and using their Sydney local.

As a disclaimer this is an independent test and I’d encourage you to do your own testing as results may vary.

### Base Line

<div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-1-1024x522.png)<figcaption>Standard – Base</figcaption></figure></div><div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-2-1024x525.png)<figcaption>High Freq – Base</figcaption></figure></div>### Basic Setup

<div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-3-1024x542.png)<figcaption>Standard – Basic</figcaption></figure></div><div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-4-1-1024x541.png)<figcaption>Standard – Multi</figcaption></figure></div>### Multi Page

<div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-5-1024x542.png)<figcaption>Standard – Multi</figcaption></figure></div><div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/Standard-vs-High-Frequency-Cloudways-Vultr-Comparison-6-1024x542.png)<figcaption>High Freq – Multi</figcaption></figure></div>## Results

<figure class="wp-block-table alignwide">|  | **Performance Grade** | **Page Size** | **Load Time** | **Requests** |
|---|---|---|---|---|
| Standard – Base | 95 | 76.1kb | 143ms | 11 |
| High Freq – Base | 96 | 60.8kb | 95ms | 9 |
| Standard – Basic | 95 | 39.6kb | 340ms | 9 |
| High Freq – Basic | 97 | 25.8kb | 104ms | 7 |
| Standard – Multi | 85 | 1.8Mb | 853ms | 48 |
| High Freq – Multi | 87 | 1.8Mb | 492ms | 46 |

</figure>Focusing on the load times as that’s the most important data here.

- Base difference – 48ms
- Basic difference – 200ms
- Multi difference – 361ms

What are your thoughts?

The new High Frequency Servers definitely live up to being faster than the Standard Servers, but is that speed worth the added financial input?

At only an extra $2/month, I think it is worth upgrading.

## Update

I’m in the process of migrating from Standard to High Frequency and just captured this site’s performance difference.

From 2.42s to 1.86s in load time, that’s a great increase! In general, web pages should load under 3s, or at the very least what is visible to the user should be loaded by then.

<div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/image-1024x542.png)<figcaption>Mr Ashley Ball – Standard</figcaption></figure></div><div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/image-1-1024x542.png)<figcaption>Mr Ashley Ball – High Freq</figcaption></figure></div>Looking at the waterfall in more detail, one of the best improvements I can see comes in from the First Time To Bite (FTTB). This is the first packet or piece of data between a person loading your website and the server.

I’ve always noticed that the Standard servers have a large FTTB and give an increased load time because of this.

<div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/image-3-1024x937.png)<figcaption>Mr Ashley Ball – Standard Waterfall</figcaption></figure></div><div class="wp-block-image"><figure class="alignleft size-large">![](https://mrash.co/wp-content/uploads/2020/08/image-2-1024x930.png)<figcaption>Mr Ashley Ball – High Freq Waterfall</figcaption></figure></div>Notice the yellow ‘wait’ time bar at the top of each screenshot.

The Standard server gives a whopping 959.8ms vs the High Freq of 356.0ms.