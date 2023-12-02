---
id: 5769
title: OhSINT Hints, Writeup, Walkthrough &#038; Notes
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5769
url: "/?p=5769"
---

Let’s go for another [TryHackMe](https://tryhackme.com/) room, this time we’re tackling [OhSINT](https://tryhackme.com/room/ohsint), which begs the question “are you able to use open-source intelligence to solve this challenge?”

This was a fun, different room for me, I love the idea of OSINT and using the web to solve challenges. Despite having a few initial issues along the way, it was fun to answer “what information can you possible get with just one photo?”

*Disclaimer, there are spoilers for this room below, please use the hints if you do not want any steps spoiled.*

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/fCAunCYeq64?feature=oembed" title="OhSINT walkthrough // TryHackMe Writeup // THM Guide" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ \[sub\] OhSINT walkthrough // TryHackMe Writeup // THM Guide – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=dce2f06b3712479fb91ce263125b40df "[sub] OhSINT walkthrough // TryHackMe Writeup // THM Guide was transcribed from audio to text using Happy Scribe")

Welcome back to the channel.

This is going to be a walkthroughof OhSINT, an easy beginner challenge CTF

in Google Dorking and gonna use someopen source intelligence to solve this.

So the only thing we have which is a bitstrange for me anyway is just an image.

So we’re starting withan image and that’s it.

So there’s no box to virtual machineto start up or anything like that.

It’s all just the flaming thing.

So I’ve already downloaded it.

Not to ruin the surprise, but I haveactually gone through this box.

I know what’s up and I will explaina few things along the way.

So we’ll go ahead and download

that and we’ll give it a bit of an insect,a bit of a hover there.

What do we got?Windows XP, JPEG.

So by the untrained eye, we don’t haveanything here, no hidden imagery.

It looks just like a pretty basic image.

So we need to use somethingto assess this little closer.

So if we look at our hint here sowe’ve got our list of questions.

So a few questions.

What is the user’s avatar of?

What is this user’s avatar of?

So it makes zero sense.

So my first intuition was like,let’s just go find it first.

So it’s just on the desktop.

So is there anything unusual about it if

we just look at it and we can run fileagainst it and it is indeed a JPEG.

So the hint here is EXIF tool.

So when we look up EXIFtool we can find that.

This is a pretty popular command lineapplication, pearl library for metadata.

So I’m not an expert in this,

but I know when we take photosthat there is more data behind the photo

than just the photo itself,the pixels and whatnot.

So we can go ahead and sudo apt install

EXIF tool like so I’vealready got installed.

So once it’s installed we can just go

ahead and look at the manpage for that EXIF tool.

We can see here itread and write meta information in files.

So not just JPEGs but all files.

So yeah, there’s a lot that this thing cando, but we can go ahead and just run it

by default against our image thereand we get some information here.

So going through this, it’s reallya case of what sticks out at us.

Okay, so this is where wesort of take our time.

So version number of the tool,the file directory, things that we already

know, the permissions we could alreadysee that nothing really unique here.

Copyright.

Now, I must admit, when I first saw that,I did sort of skip over it.

And this is sort of what’s hard aboutgoing through this stuff is it’s not like

a video game where there will be a lightshining towards

somewhere that as the player weknow that we need to go that way.

We have to use somecritical thinking here.

I honestly skipped over this.

I just went, okay,I don’t know what that is.

It’s probably not too important.Kept looking.

I was like, okay, well,maybe we’ve got some GPS coordination.

Maybe we do something with that.

And maybe this coding baseline,maybe that’s something.

But then I thought back to copyright.

I’m like, you can just sortof whatever in a copyright.

I mean, you can manipulate allthis metadata input or whatever.

But I’m like, I don’t know,I think that this is the thing.

So let’s go ahead and justdo some Google dorking.

So you can see here I’ve alreadygone to these links and this is it.

This is open source intelligence.

And it took me a little bit to get my head

around to be honest, because Ithought we were going to stay here.

And this is what I’m used to,I’m used to cybersecurity.

I’m used to learning hackingin the terminal.

Like this is where we do stuff.

But open source intelligenceis using the Internet.

So this is kind of wildfor my little brain.

The next thing I made a mistake in when

going through this is Ionly looked at Twitter.

I just saw Twitter and I just assumedthat the rest were challenges.

I didn’t even look at these other two.

So learn from me and what my future self

will be better at is actually takingthe time to look at the search results.

So we can see here we have a Twitter

profile, then we have a WordPress.comblog and then we have a GitHub repo.

And then the giveaway is these are all

anything that says tryhack me or write up.

We can confidently say that these are

people have been looking up the Gmailand some spy talks, whatever that is.

Those are just write ups.

But our focus is on these three.And this is really cool.

I have seen this in other CTFs-

from watching John Hammond videosand other YouTubers and that

this is a part of the challenge wherewe’ll have fake

Twitter accounts or Facebook accountsthat we can go and try and hack.

Let’s look at these three in order.

And if we go back to whatis the user’s avatar of?

Pretty confident out of all of our three

accounts that we can focus on that theavatar is indeed of a C.A.T. Nice.

What city is this person in now?

Again, I made the mistake of not looking

at the other options that I justwas here and I was like, what?

Oh man.

I was looking at comments and there wassome like base 64 encoded comments.

I’m like, is this a part of it?

Don’t waste your time.

This is an easy challenge after all.

So I go to deep too fast.

It’s another thing.

So let’s just flick through.

So we’ve got on this one.

I’m in New York right now,

so I will update the siteright away with new photos.

Okay, so we’ve gotHello Worlds from my house.

I can get free WiFi, and we have some sort

of MAC address lookingthing back on Twitter.

So this isn’t helping.

We can see here that they are in New York,

but our question is,what city is the person in?

It could be New York.I’m just playing.

I know it’s not.

So let’s go ahead and look over hereat the GitHub repo.

And we can see that this is the only

repo that I have, is this people finder,which I think is in spirits.

Hi, I’m from London.

That is what we’re after now,

this next one, and I got a story,BSSID plus wiggle.

Net.So this was totally new to me.

Let’s just go check out Wiggle.Net.

If we look here, we do havesome more information.

This is linking to our Twitter,talking about photos.

And here, email me if you want.

Before we go down that rabbit hole,

let’s just go over Ispelled it wrong, didn’t I?

Let’s just look up wiggle.There we go.

What’s the SSID of the WAPhe connected to.

So we need to use this website.

Okay, you will need to make an accountin order to Wiggle work,

and you do not need to use youractual personal information.

You can just go aheadand use whatever you want.

So the idea here is we have this hint,

this BSSID, which I did look up whatit stood for and I can’t remember.

But we can use this MAC addresslooking thing, put it in here.

As you can see, my other attempts paste

that in and we can querythe database to find where he’s at.

This is where I had the issue.

So if we sort of look around

the map didn’t really takeme anywhere straight away.

I can’t actually see anything on the map.

There is something in London.

And I must admit, this didnot work out well for me.

When I first did this, I punchedit in and I didn’t see anything.

And I didn’t take my timelooking around the map.

And I must admit,

it stands out now because Iknow what I’m looking for.

But if you tried this like me,

don’t feel silly that you didn’tsee it or it didn’t work.

So we can see here that this MAC address

actually does come up on theirdatabase, which is just nuts.

I was reading an article about thiswebsite, and it’s kind of crazy.

Okay, so this is actually new territory.

I don’t know how to what is the SSIDof the WAP he connected to?

So can I interact with this?

There is a name.

There is a name.

It’s very small.

I definitely didn’t copy this the first

time of the wireless accesspoint that he connected to.

So what’s his personal address?

So, we can find that out ifwe go back to his GitHub.

Interestingly enough,

if we actually go to his pull requests,there’s pull request here of that README

file where he’s added,messaged me on Twitter for my email.

Probably not a good ideato give out publicly.

We can see.

I’m a little confusedbecause it’s got it here.

So the pull request was made meaning,

but he committed it, but he didn’t,like, push it to the master branch.

So that’s why we don’t see thisgreen message instead, we still see.

I think that’s how GitHub works.

Bit of an interesting thing,just I found from poking around.

So what site did you findhis email address on?

So we found it on GitHub.

Where has he gone on holiday?

So if we go back here I’min New York right now.

New York.Oops.

You can paste it in there.

It’s all pretty straightforward.

And what is this person’s password?

Okay.

I had some issues with this room.

Like, this didn’t work for methe first time because I was silly.

It annoyed me a little bit,if I’m being really honest.

I only found this from lookingat another write up.

So if we use our inspect and we can hover

over, we can see that there is a blankarea here and indeed,

there is just a like,if we just change this to #000000

we can see here that the textis actually on the website.

It was just hidden.

So in one way, that’s cool.

Like a little thing like,

make sure you look around and inspectpeople’s websites,

you might find something like this,but at the same time, who does this?

I think that’s what sortof annoyed me about this.

I would have never, ever, ever found this.

I don’t think I would have ever found it.

Some part of me thinks I would have,

but another part of me is like,I wouldn’t have looked there because I

guess in my head,who puts a password on the front?

I don’t know.

I guess I’m probably just missedthe reason that it’s just a bit of fun.

It’s not supposed to be like,

super serious,but I guess that’s just my brain.

And I think it was really from when things

went wrong on the wiggle.net for me thatit sort of all started to spiral apart.

So I didn’t have the bestexperience with OhSINT.

I don’t think that’s at the faultof the TryHackMe or the creator.

I think it’s just more me.

But anyway, that was my experience.

It was fun to go through the first time,even though it was quite infuriating,

but I much prefer going through a secondtime and sharing it in this format.

This was much better.

It was nice when things actuallyworked out and getting to show you.

So I hope you enjoyed.

This has been OhSTIN from TryHackMe.

Go show some love to the creatorand the community.

I hope you enjoyed this video.

If you found it helpful,please let me know.

Leaving us comments.

It does help me.

It’s very motivating to see somepositive comments in the description.

If you have any feedback,like if I’ve done anything different

to you or anything like that, I’m alwayskeen to improve, so that would be great.

And the last thing for me is I havea monthly newsletter that I thought I

would let youknow about and let you in on.

If you want to, there’s a link below where

it’s just a littlefriendly monthly update.

And I still have to write last month’s.

But yeah, I’m usually on to it.

Anyway, that has been the video.Enjoy.

</div><div class="hs-embed" data-hide_video="true" data-id="dce2f06b3712479fb91ce263125b40df" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Hints

Here are some helpful hints if you need a bit of a nudge without any spoilers.

- What is this users avatar of? Check the metadata of the image, then use a search engine.
- What city is this person in? Use search results based on the metadata.
- Whats the SSID of the WAP he connected to? Zoom in on the city found.
- What is his personal email address? Check all profiles.
- What site did you find his email address on? Did you check?
- Where has he gone on holiday? Again, check each profile found.
- What is this persons password? Right-click, inspect.

## Steps

1. Enumerate image using `file`. ![https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f](https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f)
2. More enumeration using `exiftool WindowsXP.jpg` ![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56)
3. Use a search engine to find information about each profile based on the metadata above. Note, something I even missed the second time around, see the metadata in the search results. ![https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902](https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902)
4. Based on the information found on each profile/site, use [wigle.net](http://wigle.net) to search the BSSID. Take your time, unlike me who rushed and missed the purple circle on the city. ![https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5](https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5)
5. Continue to search each site/profile for this user to answer the last challenges. Use the hints above or the notes below for more, if you’re really stuck, see the video walkthrough.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>## Notes

Find metadata: `exiftool WindowsXP.jpg`

```
<pre class="wp-block-code">```
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
```

Searched: `*********` = [Twitter](https://twitter.com/owoodflint), [Github](https://github.com/OWoodfl1nt/people_finder), [WordPress](https://oliverwoodflint.wordpress.com/author/owoodflint/).

Helpful link: [OSINT: Tracking the Suspect’s Precise Location Using Wigle.net](https://www.hackers-arise.com/post/osint-tracking-the-suspect-s-precise-location-using-wigle-net)

## Reflection

As I said in the video I made a few mistakes in this room the first time around the twist… and I even missed something the second time too. There’s a good lesson in there to slow down and observe more with OSINT. Sometimes clues are right in front of us and skimming doesn’t help, a bad habit I do a lot.

The last challenge was a bit annoying if I’m being honest. It’s not a big deal and even though it’s not realistic, there’s a good lesson in there… somewhere. I think as my first OSINT room, it was really good, I’m very keen to do more challenges like this.

I was expecting a lot more involvement with the initial image, in fact, I thought most of the room was going to revolve around it. It was good using search engines though, it can be an underlooked skill when starting off in Cyber Sec.

So there it is, OhSINT, I hope you enjoyed this write-up and feel free to check out the YouTube channel for more video walkthroughs. Have a great day! This is day 53 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking, coding, and learning.