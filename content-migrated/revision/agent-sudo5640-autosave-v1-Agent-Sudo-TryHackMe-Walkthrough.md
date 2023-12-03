---
id: 5812
title: Agent Sudo // TryHackMe Walkthrough
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5812
url: "/?p=5812"
---

Welcome back to another [TryHackMe](https://tryhackme.com/) room, the challenge today is [Agent Sudo](https://tryhackme.com/room/agentsudoctf).

No spoilers below within the hints, just some good ol’ fashion hints to help you out on your agent sudo journey. For more detail, with some spoilers, see the steps section, and for everything I did, see my notes. If you prefer a video walkthrough, well that’s linked below, and if you want my personal thoughts on the room, check out the reflection via the video.

*Disclaimer, there are spoilers for this room below, please use the hints if you do not want any steps spoiled. Room creator credit: [DesKel](https://tryhackme.com/p/DesKel).*

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/PYQ51M8qTbw?feature=oembed" title="Agent Sudo // TryHackMe Walkthrough" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">[ Agent Sudo // TryHackMe Walkthrough – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=b764bacd7be54743bcb64bd390e2ee4a "Listen: Agent Sudo // TryHackMe Walkthrough was transcribed from audio to text using Happy Scribe")

Welcome back to anothertry hack me walk through.

Today we’re focusing on agent pseudo

and we are going throughthis easy box together.

So let’s have some fun,let’s hack and let’s learn.

So I’ve already set up the box and we justmake sure that it is indeed live and we

can see it if someone’s ping packetingis allowed, which in this case we are.

So we’re on the VPN,we have a little welcome message.

Beautiful, thank you.

Good to be here.

So let’s enumerate, as we always do,

we want to go ahead and seewhat’s running on the system.

So I’m just going BV verbosity orverbosity see the output of our results.

And I am in the habit of just going to runall scripts and other things against it.

So we have three open here,so we can go ahead and check that in.

Next up, how you redirectyourself to a secret page.

So page like web pages.

We can see here we’ve got SSH,or is that yes, 21 FTP SSH and then 80.

Right?

So yeah, we can confirmthat once it’s done.

So we have 21 FTP SSH ison 22 and then 84 http.

Yes.Always got to remember our protocols.

They’ll eventually sink into my brain.

Let’s go with our roomand what it’s directing us to.

Let’s go to and here we go.

Dear agents, use our own code nameas user agents to access the site.

Sorry, how do we redirect ourselves?

And this is sort of showingus the way we need to go.

And that’s why I really like this box is

it sort of has these great checkins telling us which way to go.

So user agent is what we’re after.

What is a user agent?

So this is how the actual site knows whattype of device is visiting the site.

It’s probably a very simplified wayof explaining it,

but we’re currently in the browser,so it has a user agent of a browser.

If we were on a phone,we have a user agent of a phone.

So we need to essentiallychange our user agents.

What we can do is inspect to get our web,develop tools up and over.

On the right here we’ve gotthree dot icon.

We go to more tools and wego to network conditions.

Here we have what user agents we’re using.

So if I go by default,

we’ve got different browser user agent,we’ve got all different user agents.

But what we need to do here is actuallyhave ours as something unique.

So we can uncheck use defaultand then we can just put in our own.

So it took me a little bit of figuring

out, but if you go to this,it actually tells us here on the hint.

So yeah, cool.

If we hit that and then we can hitrefresh, we can see here agents

underscore attentionPHP has now popped up.

Attention Chris do youstill remember our deal?

Please tell me Agent J aboutthe stuff as soon as possible.

Also change your goddamn password.

It’s a week from Agent Doneand numerous the machine.

Time to brute your way out FTP.

All right, so let’s goback to our results.

Usually I do spend a little bit of timegoing through here, but since I have done

this box, I didn’t spend too much timein the video, so I apologize for that.

So the tool we want to useis going to be Hydra.

Okay?This is a tool so we can run that and we

can see a bit more information here,a bit of a help menu,

and we want to specify a fewconditions to break in via FTP.

At the moment,

if we were to FTP into this, we have Chrisusername, but we don’t have his password.

The hint here is brute forcing.It’s not really a hint.

They’re telling us how to get in.

So our hydro tool, we need a few things.

So first we need to specify our user,

which is Chris,and then we need to specify our password

list that we’re goingto pass through to it.

And I’m just going to go like this.

And then we want to make sure we go

v uppercase v to see the output,just like an N map, which is VV.

And then we can specify the IP that we’re

going to, and then the typeof protocol that we’re going through.

So the last thing is the amount.

I think this is tasks or threads,how fast essentially we can do it.

I think by default it’s at 16,

and we’ll actually see the output of this,but we can go much faster at 32, 64.

And I don’t really know if this is likehow limited this is for the tool,

or it just comes down to hardware,but I’ll go 64.

Okay, I didn’t actually get it.I had an error.

So I’m going to run it and I’m going

to change the task number and thenturn it back down to 32 this time.

All right.

And there we have it, our host, our login,and our password, so we can save that off.

And now we can go ahead and go into FTP asChris and type in our password of crystal.

Great.And now we’re in.

So we can list out everythinghere and we can see a few files.

So what we can do is run Mget to grab

everything, say yes three times,get everything, and then we can go ahead

and exit out of that and see what we’vegot and what we are working with.

Great.

So when it listed out,I like to run a file star.

So for all just to have a quicklook at what we’re going with.

So we have a JPEG image, we havea PNG image, and we have a text file.

So lowest hanging fruit.

Here is our text file.

Let’s go ahead and print that out.

Just remember to put crystal in here.

So we have a zip file password.

Zip file password.Interesting.

So what we’ve copied, we don’tactually have any zip files.

So this is, I guess, a clue.

There should be something in here, right?

So let’s read our message.

Dear Agent J,all these alien look photos are fake.

Agent R store the real picturesinside your directory.

Your login password is somehowstored in the fake images.

It shouldn’t be a problem for you.

All right, so next up is somehowwe need to examine our images.

So if we go over to what they actuallylook like, we can see them here.

We need a tool to look at them properly.

So this is where I needed to cheat a bit

and find a tool because Icouldn’t find one straight away.

So bin walk was what I found.

This is able to walkthe binary of our files.

So we can see here by runningthat we have our help menu.

So we can have bin walk options and thenfiles if we just write bin walk.

And then we’ve got our two files.

So we got a JPEG and a PNG.

So if we go to that JPEG for one,

we can see here that thisholds no other information.

It’s just the image.

Okay, so let’s try again,this time looking at the PNG.

Okay, first we see our image.

But next, well, look whatis indeed hidden in here.

So we can see a zip archive file thatlooks like there’s a text file in there.

Crazy.

So if we go through the man page orthe Help page again, we can find,

I believe it’s E for extract,and we can run that.

Okay, let’s just see ifwe indeed got anything.

So running LS again does giveus underscore PNG extracted.

So let’s go.That is a directory so we can CD into it

and we can see here,indeed, we have our files.

So let’s see if there’sanything else hidden in there.

Let’s run file against everything.

So we’ve got our Z lib compressed,our zip archive data at least.

So this really got me for a while.

I was like, okay,we see that there’s nothing in the zero

bits of information in our textile,which is pretty interesting.

So our focus is here.

We can try and cap this stuff out,but it’s all encrypted or compressed,

or we can’t actuallymake anything out of it.

So we need to do something else.

We can indeed, if we lookat a hint, we see Mr.

John.Mr.

John being a great tool.

So we can actually run zip to John, and wecan run that against a zip file there.

And what that’s going to do is actuallypull out the hashes that we need to crack.

If we actually run that,but then output it into a new file.

So we can just call this, like, hash.

If we go and look at that hash filehere’s, everything in that zip format,

then it’s as simple as just runningJohn against that hash file.

So you’ll see something different, becauseI’ve already actually cracked this.

It’s already saved.

And you will indeed see on your screenthe zip file password that is alien.

So, great.

Now we’ve got our password that wecan actually get into our file.

So if we run and you mightneed to download seven zip.

So if you pseudo apt install and then go

seven zip, and this is how we’reactually going to look at the file.

And then we can run sevenZ and E for extract.

And we actually run itagainst our 3650 lib.

And we go, yes.

What’s our password?

Well, we just cracked it.

We can type that in, which was alien,and then we get something interesting.

If we look at our file all again,

we’ll notice that our text file,which had no data that was indeed empty,

this was zero bits, and this wasjust no data, now has 86 bits in it.

We actually have some ASCII text.

So if we go and cut that out here,we have agency.

We need to send the pictureto something as soon as possible.

All right, so this is our next clue.

We need to do something with this so we

can actually throw this into a hash valueand we can find that this is base 64.

So what we can do is echo that and pipe itthrough a base 64 Tool and then decode it.

And here, indeed, we have our Area 51.

Great.

So what do we do now?

Well, we have a password.

And if we remember that,we had another image.

So if we can see here,let’s go back to that image,

let’s CD back, and let’s actually unlockthe password using something for stag.

So after a bit of research,

I found Steg Hide was the toolthat we were looking for.

So we want to extract from this JPEG image

the data that’s hidden in here,so we can run it using SF.

So it’s just specifying the filethat we want to open, which is our Jpg.

And then we want the password,which, as we just got, was Area 51.

Look at that rate.Extracted data to message TXT.

So we list out our files here.

We have our message TXT.

Let’s go ahead and run that.

And indeed, we get our second name, James.

All right, glad you found you.Find this message.

Your login password is hackerrulls.

SSH password.

Don’t ask me why the password look cheesy.

Ask Agent R to set this passwordfor you, your buddy, Chris.

Okay, so now it’s telling us where to go,which in this case is SSH.

And we are going to be loggingin as James with our new password.

That we found of hackerrulls explanation.

Mark all right, it’s task four,capture the user flag.

You know the drill.

So we’ve successfully SSHedinto and we have two things.

The user flag.Great, that’s easy.

Let’s go and cut that out and grab that.

Next, what is the incidentof the photo called?

So, in order to get this photo and open it

up, I’m not sure how to do itwhen we’re SSH if we can do it.

So what we can do in turn is wecan actually just copy this over.

So if we go back to our terminal,we can run secure copy,

we can use the R and we can log into Jamesand we can log in at our IP address.

And we need to specify usually we go like

home James because this is wherethe file is that we want to get.

But in this case,if you just leave it blank,

it’s the directory, and then this isthe directory that we want to copy it to.

Password is hacker rules.Cool.

So that’s copied over everything,including the images, what we’re after.

I had a bunch of trouble with this.

So this is the recursive switch that I’ve

just used because this is the onlyway I could get it to work.

But hey, it does the trick.

So now we’ve copied over our JPEG,

we can just navigate thereand we get this creepy image.

Now, this image didlook a little familiar.

I’m like.I swear I’ve seen this.

And if we look at our hints,it says to reverse image and Fox News.

So I’m like, okay,this is an article somewhere.

So I was recently just watchingand posting video on David Bumble’s

channel, and they actuallyrecommend Bing search.

So there is some use for Bing.

So if we plug in this image,we can start to see some similar results.

And it’s a pretty common image.

So the first thing I saw herewas most famous UFO hoax.

I was like, okay, that’sprobably where I’ve seen it.

So if we look up Fox News alien hoax,

we can see here we havethe Roswell alien autopsy.

So this is the Fox News articlethat they’re referring to.

Great.So that’s just a little bit of fun.

That doesn’t actuallylead anywhere further.

So next up, we’ve got taskfive privilege escalation.

Time to get real.

So CVE number for escalation.

So this really stumped me.

I had no idea what to do,

but I remembered from the last capturethe flag I did running

L with the pseudo command willshow up indeed what we can run.

And when we run that,we can actually run bin bash.

So with a bit of a search of exploit bin

bash, we can find indeed,we have a security bypass for Sudo 1827.

Now, I only knew this because I’vedone other capture the flags.

I’m not sure how else to discover this.

And we can indeed confirmthat this is the right one.

It says here that we can take advantage ofit by simply running the exploit of this.

So if you copy that into a terminalthat indeed switches us over to root

change directories into our route,we can indeed see our root text.

So if we go and cat that out, we have to.Mr.

Hacker, congratulationson reading this box.

This was hackney, blah, blah, blah.

Your flag is this.

We can submit that and we have indeed

the creator of the boxHell as our last bonus.

So there we go.There was agent pseudo trihack me room.

I hope you enjoyed this, I hope youlearnt something along the way.

This was actually one of my favorite CTFsbecause I did cheap and I really

tried to get through it and I foundthe flow of this room to be really good.

I enjoyed the hints.

They didn’t give too much away.

They also weren’t too mysterious that you

didn’t quite understandwhat you needed to do.

So there was a good balance betweenbeing challenging and enjoying.

So I’m excited to go on to more tria rooms

that are of this sort of qualityin this sort of format.

So, yeah, if you like this sort of thing,please let me know

if you have any questions or any issues,anything did make sense, please ask.

I’ll do my best to answer.

Otherwise, if you would like to subscribe,that would be awesome.

I have a monthly newsletter if you’d like

to subscribe to that, which I talk aboutcybersecurity and my learning path.

So there’s some good info there.

Otherwise, please reach out overTwitter if you would like to chat more.

Always keen to get to know otherpeople learning inside security.

So, with all that being said,

have a wonderful day and Iwill see you in the next one.

Bye.

</div><div class="hs-embed" data-hide_video="true" data-id="b764bacd7be54743bcb64bd390e2ee4a" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Hints

Task 2 Enumerate

- How many open ports? `nmap` can show you.
- How you redirect yourself to a secret page? Read the note on `index.html`
- What is the agent name? Use the web dev tools to change `user-*****`

Task 3 Hash cracking and brute-force

- FTP password. Use `hydra` with `rockyou.txt`
- Zip file password. Use `binwalk` to *really* see the `png`, then `zip2jon`.
- steg password. Use `steghide` to *really* see the `jpg`.
- Who is the other agent (in full name)? `cat` your new `message.txt`
- SSH password. `base64 -d`

Task 4 Capture the user flag

- What is the user flag? Once in, simple `cat`
- What is the incident of the photo called? Use OSINT via bing.

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>Task 5 Privilege escalation

- CVE number for the escalation. `sudo -*`
- What is the root flag? `cat /root/root.txt`
- (Bonus) Who is Agent R? see `root.txt`

## Steps

1. Task 2 Enumerate, as always, start by scanning the machine, I used `nmap -vv -A <ip>`. We can see ports 21, 22 and 80, so most likely we have a web server running, let’s confirm this.
2. Visithttp://&lt;ip&gt; to get the next clue, change the user-agent by going to Inspect (DevTools) &gt; Customise and control DevTools &gt; More Tools &gt; Network conditions, User agent. Here you can change the user-agent by disabling/unchecking Use browser default. Reload the page, and you’re done!
3. Task 3 Hash cracking and brute-force. Now that leads us back to port 21, ftp, so now armed with a username, let’s use brute force. Use hydra -t 32 -l \*\*\*\*\* -P /usr/share/wordlists/rockyou.txt -vV &lt;ip&gt; ftp against the target and you’ll be able to find the password, so then log in using ftp &lt;ip&gt;, and mget \* to copy all the files.
4. It’s time to examine what we’ve found, run file \* to show some basic info, but use binwalk to show hidden info within the files. Then binwalk -e cutie.png to pull out the data, again running file \* will help here with new files. Use zip2john 8702.zip &gt; 8702.hashes to extract the hash, then john 8702.hashes to crack it.
5. The new text file provides a cryptic message, we can decode this using echo \*\*\*\*\*\*\*\* | base64 -d. That’s the steg password, use `steghide extract -sf cute-alien.jpg -p ******` to gain SSH creds, then `ssh *****@<ip>`. Next up, Task 4 Capture the user flag.
6. Now copy the files over via `scp -r * *****@<ip>: .`, use a bit of OSINT and find the CVE. For more, use my notes below or hints above for help, enjoy!

## Notes

nmap: `nmap -vv -A <ip>`

```
<pre class="wp-block-code">```
Completed NSE at 02:52, 0.00s elapsed
Nmap scan report for 10.10.253.182
Host is up, received conn-refused (0.32s latency).
Scanned at 2022-07-06 02:51:25 EDT for 42s
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE REASON  VERSION
21/tcp open  ftp     syn-ack vsftpd 3.0.3
22/tcp open  ssh     syn-ack OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 ef:1f:5d:04:d4:77:95:06:60:72:ec:f0:58:f2:cc:07 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC5hdrxDB30IcSGobuBxhwKJ8g+DJcUO5xzoaZP/vJBtWoSf4nWDqaqlJdEF0Vu7Sw7i0R3aHRKGc5mKmjRuhSEtuKKjKdZqzL3xNTI2cItmyKsMgZz+lbMnc3DouIHqlh748nQknD/28+RXREsNtQZtd0VmBZcY1TD0U4XJXPiwleilnsbwWA7pg26cAv9B7CcaqvMgldjSTdkT1QNgrx51g4IFxtMIFGeJDh2oJkfPcX6KDcYo6c9W1l+SCSivAQsJ1dXgA2bLFkG/wPaJaBgCzb8IOZOfxQjnIqBdUNFQPlwshX/nq26BMhNGKMENXJUpvUTshoJ/rFGgZ9Nj31r
|   256 5e:02:d1:9a:c4:e7:43:06:62:c1:9e:25:84:8a:e7:ea (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBHdSVnnzMMv6VBLmga/Wpb94C9M2nOXyu36FCwzHtLB4S4lGXa2LzB5jqnAQa0ihI6IDtQUimgvooZCLNl6ob68=
|   256 2d:00:5c:b9:fd:a8:c8:d8:80:e3:92:4f:8b:4f:18:e2 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOL3wRjJ5kmGs/hI4aXEwEndh81Pm/fvo8EvcpDHR5nt
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 02:52
Completed NSE at 02:52, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at <https://nmap.org/submit/> .
Nmap done: 1 IP address (1 host up) scanned in 42.85 seconds

```
```

Visit: `http://<ip>` Changed User-Agent \[[Link](https://www.searchenginejournal.com/change-user-agent/368448/)\], redirected: `http://<ip>/agent_C_attention.php`, Found name Agent C.

```
<pre class="wp-block-code">```
Attention *****,

Do you still remember our deal? Please tell agent J about the stuff ASAP. Also, change your god damn password, is weak!

From,
Agent R

```
```

Crack FTP: `hydra -t 32 -l ***** -P /usr/share/wordlists/rockyou.txt -vV <ip> ftp` \[[LINK](https://www.binarytides.com/crack-ftp-passwords-with-thc-hydra-tutorial/)\]

```
<pre class="wp-block-code">```
[21][ftp] host: <ip>  login: *****   ****password: *****

```
```

Logged into FTP `ftp <ip>`, ran `mget *` to get all the files.

Examine images: `binwalk`, extracted image data: `binwalk -e cutie.png`.

Installed `sudo apt install 7zip` \[[Link](https://ubuntuforums.org/showthread.php?t=1416364), [Link](https://super-unix.com/ubuntu/ubuntu-extracting-zip-file-fails-giving-error-need-pk-compat-v5-1/)\] `7z e 365.zlib`.

Cracking zip file \[[Link](https://dfir.science/2014/07/how-to-cracking-zip-and-rar-protected.html)\]: `zip2john 8702.zip > 8702.hashes`, `john 8702.hashes`

```
<pre class="wp-block-code">```
Using default input encoding: UTF-8
Loaded 1 password hash (ZIP, WinZip [PBKDF2-SHA1 256/256 AVX2 8x])
Cost 1 (HMAC size) is 78 for all loaded hashes
Will run 4 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
*****            ****(8702.zip/To_agentR.txt)     
1g 0:00:00:00 DONE 2/3 (2022-07-08 01:35) 2.222g/s 101044p/s 101044c/s 101044C/s 123456..ferrises
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

```
```

`cat To_agentR.txt`

```
<pre class="wp-block-code">```
Agent C,

We need to send the picture to **'********'** as soon as possible!

By,
Agent R

```
```

Finding hash value: `echo ******** | base64 -d`, `steghide extract -sf cute-alien.jpg -p ******`.

```
<pre class="wp-block-code">```
Hi *****,

Glad you find this message. Your login password is ****************

Don't ask me why the password look cheesy, ask agent R who set this password for you.

Your buddy,
*****

```
```

Connect via SSH: `ssh *****@<ip>`, copy over image: `scp -r * *****@<ip>: .` \[[Link](https://youtu.be/gGe1cNgfHwE), [Link](https://www.freecodecamp.org/news/scp-linux-command-example-how-to-ssh-file-transfer-from-remote-to-local/)\].

Ran `sudo -*`, searched ‘exploit sudo \*\*\*\*\*\*\*\*\*\*\*\*’, found exploit `sudo ***** *********`

```
<pre class="wp-block-code">```
To Mr.hacker,

Congratulation on rooting this box. This box was designed for TryHackMe. Tips, always update your machine. 

Your flag is 
********************************

By,
****** a.k.a Agent R

```
```

This is day 54 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking, coding, and ‘learning.