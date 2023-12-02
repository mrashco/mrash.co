---
id: 5591
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5591
url: "/?p=5591"
---

Let’s go for another [TryHackMe](https://tryhackme.com/) room, this time we’re tackling [OhSINT](https://tryhackme.com/room/ohsint), which begs the question “are you able to use open-source intelligence to solve this challenge?”

This was a fun, different room for me, I love the idea of OSINT and using the web to solve challenges. Despite having a few initial issues along the way, it was fun to answer “what information can you possible get with just one photo?”

*Disclaimer, there are spoilers for this room below, please use the hints if you do not want any steps spoiled.*

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

1. Enumerate image using `file`. ![https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f](https://p146.p4.n0.cdn.getcloudapp.com/items/llu0EwLv/8e5a9af0-1bd5-400c-a7b0-a54f1834b5b0.jpeg?v=ddada66672d624c871a6f0916d13d85f)
2. More enumeration using `exiftool WindowsXP.jpg` ![https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56](https://p146.p4.n0.cdn.getcloudapp.com/items/xQuwqv28/775a3765-c64b-4e4c-ab25-3ace2f770f0a.jpeg?v=89d301d262a1343f4dbc9a04bedebb56)
3. Use a search engine to find information about each profile based on the metadata above. Note, something I even missed the second time around, see the metadata in the search results. ![https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902](https://p146.p4.n0.cdn.getcloudapp.com/items/RBumn0QZ/6c5c8dc7-af30-4ae9-a2f1-8299c3ea3369.jpeg?v=90f04c7cecd1c1e62d27459f05813902)
4. Based on the information found on each profile/site, use [wigle.net](http://wigle.net) to search the BSSID. Take your time, unlike me who rushed and missed the purple circle on the city. ![https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5](https://p146.p4.n0.cdn.getcloudapp.com/items/YEukrvnx/4eb58239-0c29-41e1-96b5-f304043fc4d7.jpeg?v=929909124e698525a3942eccaf62dfb5)
    1. Continue to search each site/profile for this user to answer the last challenges. Use the hints above or the notes below for more, if you’re really stuck, see the video walkthrough.

## Notes

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

Searched: `*********` = [🔗 Twitter](https://twitter.com/owoodflint), [🔗 Github](https://github.com/OWoodfl1nt/people_finder), [🔗 WordPress](https://oliverwoodflint.wordpress.com/author/owoodflint/).

Helpful links: [OSINT: Tracking the Suspect’s Precise Location Using Wigle.net](https://www.hackers-arise.com/post/osint-tracking-the-suspect-s-precise-location-using-wigle-net)

## Reflection

As I said in the video I made a few mistakes in this room the first time around the twist… and I even missed something the second time too. There’s a good lesson in there to slow down and observe more with OSINT. Sometimes clues are right in front of us and skimming doesn’t help, a bad habit I do a lot.

The last challenge was a bit annoying if I’m being honest. It’s not a big deal and even though it’s not realistic, there’s a good lesson in there… somewhere. I think as my first OSINT room, it was really good, I’m very keen to do more challenges like this.

I was expecting a lot more involvement with the initial image, in fact, I thought most of the room was going to revolve around it. It was good using search engines though, it can be an underlooked skill when starting off in Cyber Sec.

So there it is, OhSINT, I hope you enjoyed this write-up and feel free to check out the YouTube channel for more video walkthroughs. Have a great day! This is day 52 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking, coding, and learning.