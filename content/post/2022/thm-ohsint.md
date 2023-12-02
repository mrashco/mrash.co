---
title: OhSINT Hints, Writeup, Walkthrough &#038; Notes
author: Mr Ash
type: "post"
published: 2022-07-05
lastUpdated: 2022-11-05
url: "/ohsint/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/2NumzrQ1/9f7bd99d-6227-40ef-9519-8c21e9d72a6b.png?v=2b7ea1e3bcb951f6a3c7016a90e9105c
categories: Cyber
tags:
    - Hacking
    - TryHackMe
    - Capture The Flag
    - Walkthrough
---

Let’s go for another [TryHackMe](https://tryhackme.com/) room, this time we’re tackling [OhSINT](https://tryhackme.com/room/ohsint), which begs the question “are you able to use open-source intelligence to solve this challenge?”

This was a fun, different room for me, I love the idea of OSINT and using the web to solve challenges. Despite having a few initial issues along the way, it was fun to answer “what information can you possible get with just one photo?”

*Disclaimer, there are spoilers for this room below, please use the hints if you do not want any steps spoiled.*

<!-- <figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/fCAunCYeq64?feature=oembed" title="OhSINT walkthrough // TryHackMe Writeup // THM Guide" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ \[sub\] OhSINT walkthrough // TryHackMe Writeup // THM Guide – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=dce2f06b3712479fb91ce263125b40df "[sub] OhSINT walkthrough // TryHackMe Writeup // THM Guide was transcribed from audio to text using Happy Scribe") -->

<!-- </div><div class="hs-embed" data-hide_video="true" data-id="dce2f06b3712479fb91ce263125b40df" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style> -->

## Hints

Here are some helpful hints if you need a bit of a nudge without any spoilers.

- What is this users avatar of? Check the metadata of the image, then use a search engine.
- What city is this person in? Use search results based on the metadata.
- Whats the SSID of the WAP he connected to? Zoom in on the city found.
- What is his personal email address? Check all profiles.
- What site did you find his email address on? Did you check?
- Where has he gone on holiday? Again, check each profile found.
- What is this persons password? Right-click, inspect.

## Steps

1. Enumerate image using `file`. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f](https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f)

2. More enumeration using `exiftool WindowsXP.jpg` 

![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56)

3. Use a search engine to find information about each profile based on the metadata above. Note, something I even missed the second time around, see the metadata in the search results. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902](https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902)

4. Based on the information found on each profile/site, use [wigle.net](http://wigle.net) to search the BSSID. Take your time, unlike me who rushed and missed the purple circle on the city. 

![https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5](https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5)

5. Continue to search each site/profile for this user to answer the last challenges. Use the hints above or the notes below for more, if you’re really stuck, see the video walkthrough.

<!-- <div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts -->

 <!-- </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/) -->
<!-- - [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
  -->
 <!-- </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts -->

 <!-- </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/) -->
<!-- - [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
  -->
 <!-- </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know. -->
 
## Notes

Find metadata: `exiftool WindowsXP.jpg`

```text
ExifTool Version Number         : 12.42
File Name                       : WindowsXP.jpg
Directory                       : .
File Size                       : 234 kB
File Modification Date/Time     : 2022:07:04 01:49:32-04:00
File Access Date/Time           : 2022:07:04 01:49:34-04:00
File Inode Change Date/Time     : 2022:07:04 01:49:33-04:00
File Permissions                : -rwxrw-rw-
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
XMP Toolkit                     : Image::ExifTool 11.27
GPS Latitude                    : 54 deg 17' 41.27" N
GPS Longitude                   : 2 deg 15' 1.33" W
Copyright                       : **************
Image Width                     : 1920
Image Height                    : 1080
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 1920x1080
Megapixels                      : 2.1
GPS Latitude Ref                : North
GPS Longitude Ref               : West
GPS Position                    : 54 deg 17' 41.27" N, 2 deg 15' 1.33" W
```

Searched: `*********` = [Twitter](https://twitter.com/owoodflint), [Github](https://github.com/OWoodfl1nt/people_finder), [WordPress](https://oliverwoodflint.wordpress.com/author/owoodflint/).

Helpful link: [OSINT: Tracking the Suspect’s Precise Location Using Wigle.net](https://www.hackers-arise.com/post/osint-tracking-the-suspect-s-precise-location-using-wigle-net)

## Reflection

As I said in the video I made a few mistakes in this room the first time around the twist… and I even missed something the second time too. There’s a good lesson in there to slow down and observe more with OSINT. Sometimes clues are right in front of us and skimming doesn’t help, a bad habit I do a lot.

The last challenge was a bit annoying if I’m being honest. It’s not a big deal and even though it’s not realistic, there’s a good lesson in there… somewhere. I think as my first OSINT room, it was really good, I’m very keen to do more challenges like this.

I was expecting a lot more involvement with the initial image, in fact, I thought most of the room was going to revolve around it. It was good using search engines though, it can be an underlooked skill when starting off in Cyber Sec.

So there it is, OhSINT, I hope you enjoyed this write-up and feel free to check out the YouTube channel for more video walkthroughs. Have a great day! This is day 53 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking, coding, and learning.