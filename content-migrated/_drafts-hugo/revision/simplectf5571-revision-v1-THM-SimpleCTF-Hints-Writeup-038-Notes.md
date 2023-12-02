---
id: 5770
title: THM SimpleCTF Hints, Writeup &#038; Notes
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5770
url: "/?p=5770"
---

Welcome back to [TryHackMe](https://tryhackme.com/), this time it’s [SimpleCTF](https://tryhackme.com/room/easyctf)… or as I’d call it ‘Not So SimpleCTF’… as I had a few issues getting this CTF to work.

Let’s dive into it.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/bWVXSoBoAk4?feature=oembed" title="SimpleCTF Walkthrough THM" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:600px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ Listen: SimpleCTF Walkthrough THM – powered by Happy Scribe](https://www.happyscribe.com/?utm_source=embed-player&utm_term=cf0f9007980c47a2bdb42aee378367de "Listen: SimpleCTF Walkthrough THM was transcribed from audio to text using Happy Scribe")

Hi, welcome back.

We are going to be going through

the simple CTF on Trihack Me,which is a beginner level CTF.

This has been a good room to go through.

There was a few notes,not so simple areas which we’ll get

into and after a little bitof research, we got through.

If you like this video,please do leave a like and subscribe

and a comment with your thoughts,feelings and feedback.

All right, we only have one task,

as this is not a walk through,just an actual CTF, which is nice.

So we want to start offby getting our machine.

So make sure you’re logged into yourTry Hackney account,

boot that machine up and we’llstart looking at these questions.

So as that’s booting up,let’s go ahead and go into our open VPN.

Now, if you have issues with this, I willactually just show you some command.

You can go ahead and run this.

I fixed my issue up.

The issue that I was having was

I wasn’t seeing an initializationsequence completed at the end.

It was sort of stuck in a loop.

So I reached out to the discord community

and they sent that throughand that worked great.

It looks like it’s sort of like a findand replaced from my understanding.

But you need to run this insidethe location of your OVPN file.

So if you ever have that issue,that’s a nice little fix there.

Once you’re on, make surethat you can connect.

You are connected by Pinging Ten

and also make sure that you cansee the VM that started up.

Now I have done this room,

so we should seeour package there and it just does take

a little while sometimes, so firstfew packets dropped, but all good.

So we are up and runningso to see how many ports,

we’re always going to start off with ourenumeration, which is going to be

finding out as much as wewant about this machine.

So I’m going to make sure I do the double

verbosity, making surethat we see our outputs.

I’m going to run capital A for all so OSdetection and trying to run scripts so

it’ll do a bit of automated probing,looking around for us.

Great.So I’m going to let that run.

This shouldn’t take too long

now that we’ve confirmedthat everything was open.

Unlike me, I didn’t confirmthings and I just started.

Okay, so we’ve got a fewports already here.

So the first question we’ve got, how manyservices are running under port 1000?

Well, so far I can see two underneath1001 over, so let’s go check it too.

Great.

Now next, what is runningon the higher port?

So we can’t see what’s running on ourhigher port until this completes.

So at this point we’ve seen the discovered

ports and now it’s running throughthe extra.

So it’s trying to find scriptsthat are going to match these ports.

It’s going to do its best jobto see what’s up with that.

So here we go.

We’re nearly finished.

Awesome.

So this is a good time to goahead and grab all of that.

I did output it to a file, but youcan copy paste this into your notes.

I do this, I’ve got allmy notes as I go along.

But for this purpose of this video,

I will not be taking notes becausejust add a little bit too much time.

Okay.

So we can go here and see our portis on SSH.

So this is a good reminder because we willmost likely I know we will be connecting

by this later on when weget some credentials.

So we’ve got to make sure we rememberthat the default port has changed.

So they’ve changed on their machine.

So this is where it gets a littlebit difficult from this point on.

What’s the CVE you’re usingagainst the application.

So out of this info, we need to startpoking around and see what we can find.

So the information that we’ve gothere so far is our three ports.

So like I said, we can’t do anythingwith SSH, so let’s focus on 21 and 80.

So we’ll go in the list in order.

So with our FTP,because we ran that capital A in the Nmap

scan, it tried to run FTP add on script,which was successful.

So we can log in to our FTP with itand just with the autonomous login.

So this is cool.

So let’s run FTP against our IP.

I think it’s capital Nonand we’re in, which is very cool.

Now we should be ableto list out the contents.

And looking at other write ups,

we actually should havebeen able to see stuff.

I’m not sure why this entersinto some passive boom.

I’m not sure if that’s an error on the BMor I’m doing something or it is by design,

but I can’t get anythingfrom looking around here.

SoI believe there is a note here that we’re

supposed to read, but from my angle,I can’t see anything.

So it’s a dead end for me.

Since I’ve gone through this.

I know that it’s not goingto be the end of the world.

We will be able to get through the box.

But it was a little confusing,very confusing in the beginning.

But that’s okay.We can sort of sort of ignore FTP for now.

So let’s look at what else we’ve got.

So it’s always good.

I try and take notes of or at leastbecause I copy this whole thing.

I’ll bold this anywhere that I see,

just version numbers of software,I’m like, okay, there could be some known

vulnerability because this is asking usabout a CVE, which if you’re unfamiliar,

is common vulnerabilitiesand exposures CV.

So it’s sort of like the publicdatabase of all known vulnerabilities.

So any version number might correspond or

link up to a knownvulnerability on that database.

Okay, so if we go over to our browser,we’ll just plug in the IP address

and we’ve just gotthe default Apache home page.

So there’s nothing there.

This is just the index HTML.

So unless we manually start just guessing

other pages like admin orthis could take a while.

Right?So let’s try and automate this guessing.

And we’ll use another tool for this.

So this is a good timeto make sure you copy this.

Over.

I’ve got a copy of this off screen,so I’m not going to do it.

So when we are, we’ve got a few tools,

we’ve got derbuster, I preferdirectory search.

I find that this one is just a littlebit easier to use and it’s pretty easy.

We’ve got to specify the URLthat we want to give to it.

In this case it’s just going to be Httpand then the IP address.

And that’s it.

The scan is nearly complete and we’vegot a few interesting things.

So we’ve already tried the index HTML,

which is just the home page,something I actually missed on our scan.

So I should have spent a bit more timeon our original Nmap scan.

So there’s more information there,but we can get

to robots TXT, so this doesn’treally give us too much information.

This also showed up on ourend map scan, which I skipped over.

But yeah, the more importantthing is this simple.

So that’s kind of interesting.

Let’s focus our efforts here because we do

have a which is a different message,

which I don’t know off the topof my head should look it up.

If somebody can, that’d be great.

So we have CMS made simple.

So content management system.

So like WordPress or Joomlacontent management system.

The technology itself isn’t too important.

It is a hint, but we don’t reallyneed to know the ins and outs of it.

Some things that I’m seeing that I didn’t

see the first time around iswe actually do see a user.

So this is a good hint.

Maybe they’ve used this asthe username for logins too.

So we can try that.

And if we have a look around,we also do get a version number,

which is something that wealways want to look for.

Usually I like to do like an inspectand just see if they’ve left any hints,

but because this is testing a knownvulnerability,

I think we’ve got everything weneed to go onto the next step.

So let’s go back to our terminal again,

make sure we’re copy pasting or outputtingour file, our information somewhere.

So looking at our database using search,

so this is going to look for our CBS.

So I did a lot of trial and error on this,

but what I found work is just startingthe searches a bit more broad.

So I was using the version number,but I sort of learned here.

Focus on the actual technology name firstand then you can start to Whittle down.

Okay, so we actually can look at all

of these in more detailby using command like

W and this will actually pull upthe link to the actual website.

So after going through almost all

of these, I can tell you that thisone is what we’re after.

So this only came from trial and errorsometimes what it’s like.

So we can go ahead and go to this and we

get our CVE,which makes sure that you’re actually

copying the full,including the actual letters CVE.

Great, awesome.

So we can go ahead and download this,

we can look at the code so weknow that this is the right one.

And this is written in Python,which I’m learning.

So this was actually a goodexercise for me to go over this.

So what we actually just want to do is

just run this without W and wejust want to locate this file.

So with search and if you’re usingKali Linux, this has got a local copy

of all of these files already,which is quite nice.

So to go and find exactly where this is,

we can use locateand we can just run that and it will go

ahead and find the absolutefile path to that.

So what we can do is if you go aheadand make like a new directory.

For example.Just try Hackney directory.

You can be as organized as you want.

But if we just go ahead and copy thatfile to our local directory.

We’re going to make somechanges to this exploit.

But we don’t want to change the original.

So we’ll just go and make a copy of that.Cool.

So if we look at this,we can get some information.

So we got comments about who madeit and what it’s made for.

We’ve got the modules that it’s using,so it’s using some request modules

and some other things justto make the output pretty.

This is cool.So this is how we’ve actually got our

sysagv working, beingthe actual terminal inputs from the user.

So when we put in you after we run this,this is how it’s actually going to use it.

So, yeah, I’m learning it’s a good

exercise to do a little bitof examination on the exploit.

The reason that I’m doing this with you is

as we run this, we’ll see ifthis is a bit of a problem.

These print functions are in Python two,this whole thing is in Python two.

So if we run Python,

we’re getting this missingparenthesis and call for print.

So it took a little while for me to figureout, but yeah, this is written in Python

two and our systems are mostlikely running Python three.

So we can force Python twoand run it like this.

But we run into another issue where these

modules that I just showed,they haven’t actually been imported.

So these are other Python files that need

to be installed in your system sothat this Python file can run.

Are You With Me?

Yes.

After lots of trial and error.

The best way to solve this is actually

to get an app called Two to Three,which I already have installed.

So go ahead and run.Sudo app install two to three and as you

may have guessed, this isliterally Python Two to three.

So it’s going to convert this filefrom Python two to three.

So once that’s installed,we just want to run two, two, three,

make sure we use uppercase W,and then put it to the file that we want.

This is actually going to show us

everything in the old file by thisminus So this is what it was.

And with the plus.This is what we’ve changed it to.

So we can see here it’s added those endparentheses to be python three compliant.

So we list that actually goes aheadand makes a backup of our file.

And along with that new file,

which it’s made those changes to So again,we can just count that out and we can see

those parentheses have beenadded, which is great.

So that saves us a lot of hassle

for manually going through,which I did consider at one point.

So Now That We’ve Got Our Python TwoExploit converted Into Python Three

we Can Go Ahead And Run Our Python Threeinterpreter as Per Normal.

And like we saw in our code,

we need to specify URL with a Uand we’re going to be passing through.

And you can see my earlier example.

We’re going to pass through

going to the Simple Directory sowe can go ahead and run that.

Now.

If yours doesn’t work,you should start to see it trying.

And this is from thepretty output the code that the exploit

developer actually made it so we can seewhat’s going on, which is quite nice.

If you don’t see anything,

if you don’t see these numbers and letterschanging, then your exploit isn’t working.

Go back and follow the steps.

Just as a little bit of a warning,

I did try this a few times,and I got different results.

So what this is going to do is it’s goingto find the salt,

the username, the email and thenthe password, which we’ll see shortly.

Great.So now we have our salt and our hash.

We can go ahead and continue.

So let’s just go back to our questions.

So we’ve got to what kind of vulnerabilityis application vulnerable.

So if we remember from ourCde, we have our SQL injection.

I was looking for this trip me up because

it was like SQL I and turns out,yeah, that’s what we’re after.

So it’s just the acronym.

Great.

So now that we have our salt,make sure we go and save this off.

We have our password and if we understand

the basics of how passwords are stored,this is the password as a hash or hash

value, and this is addedto that password for complexity.

So this exploit has taken advantage

of the commonknown vulnerability to extract this.

So what we need to do is take these values

and put it through some sortof tool where we can crack.

So a great tool for this is the hashcat.

So we can go ahead and run hashcat and we

can just put these in there,use the right settings.

There’s so many settings in hashcat.

I’ve just run the help here and I’m going

to scroll up just to seethe flags that we need.

The main two flags from doing a littlebit of research is our M and our A.

So we need to tell hashcatwhat hash type this is.

Now, I know that this isMD Five from trial and error.

And I had a little bit of a funnyerror when I first did this.

I got a different salt.

I got like half the passwordand this said M Five.

Now I assume just an error in the exploit,

but that M Five was enough for me to go,oh, well, this must be MD Five,

which is like a known,not very secure hashing algorithm.

So I went and I found it with that.

But it turns out after writing this again,

m Five was not the usernameand it was not a clue.

It was just a happy accident.

So, yeah, that’s how I knew it.

But this sort of strange thing anyway,

so we’ll be using V and Dasha for attackmode, so telling it how to attack.

So there’s examples here.

So if we scroll down to honestly, it’skind of overwhelming how many options.

So zero is MD Five,but since we have a hash and assaults,

we need to do somethinga little bit different.

And if we go through our examples,we can see here ten MD Five password

and then the salt,or 20 the salt and then the password.

So we can do it.

I did it with 20 because I was following

a guide, but let’s tryand use ten this time.

So we use password and sold becausethis is how I learned passwords stored.

It was password firstand then salt at the end.

But I guess that, you know,salts can be at different areas.

We can have multiple salts.

So let’s type out hash cat and we’ll doand we’ll go A.

So this is the important one.

So we’re just going to leave it in zeroattack mode,

which is just the straightforward one,M to specify the mode that we want.

So like I said, we could do 20,but this time I’m going to try ten.

And this is where we’re going to put

in the hash here, separatedby colon and then the salt here.

So that’s how we need this to go.

So if you haven’t saved your hash and salt

from earlier offscreen, then you needto run it again or go get it again.

So that’s the salt.

But remember, we’re doing hash and salt.

Let’s go get the hash.

So paste that in here,

separated by semicolon rather,and then the hash at the end.

Cool.

So you can go aheadand add this to a file.

So if you’re doing multiple hashes

and salts you’re trying to crack,you can just pass through the file.

We’re just trying to do one.

So that’s all we need.

Then we need to specify the wordlist.

So we actually don’tneed to do any switches.

We can just go ahead and putin the word list here.

So you can actually do this.

If we look at the hint,we can go ahead and use the SEC lists,

which is a separate directory thatfor me wasn’t installed on Carly.

So if you want to go ahead and use whatthere you go, that’s where I installed it.

If you want to go and use what theyrecommend, you can go ahead and run Siri

apt install checklists to grabthat and then you’ll have it.

So that works fineand also Rocky works fine.

So if we just list out in our user sharedlists, you should see a Rocky text.

If you’re new to Linux and you’ve had

a fresh install of Kali,make sure you go and do a G zip.

There we go.

This is from when I did it.

So you’re going to decompress or unzipthe Rocky text file, which comes zipped.

I’m not really sure why it comes,maybe it’s just for size reasons.

But anyway, you need to run this, unzipit, and then you get your text file.

Okay, so I’m just goingto use a Rocky text list.

So we’ll just go user share wordlistsand then it’s just right there.

Rock you cool.

So the last thing is we’re just goingto add show so we can see the results

at the end and yours willtake a little bit longer.

Mine’s already, I’ve done it before.

So you can see here at the end it’sadded the password, which is quite cool.

So we can go ahead and just copythat over, or rather just type it out.

So we’ve got our password.

So where can you loginto the details of the team?

So we have another three letters.

So this confused me for a bit because weknow that there is actually an admin here.

We knew that from somewhere.

If we run direct research again,we could find it that way.

I think I found itfrom just clicking around.

So you can see here when I thought M fivewas the but it’s definitely not M five.

So we can log in here.

So this is what tripped me up, becausethe questions asking for three letters.

I was like, CMS,is this where we’re going?

But if we actually go back to ourport scan, we can log in another way.

Do you remember what it is?

Pause the video and leave a comment below.

Otherwise you can justwatch me answer it for you.

So we can access SSH.

So now we have ouruser, we can go ahead and just log in.

Right, that doesn’t seem to be working.Why is that?

Go back over your scan.

What was in your scan?

That was a little bit different.

Do you remember?

The port number was different?

They added a custom port number.

Okay, so you need to specifyand it tripped me up.

So we can go ahead,put in his passwords and we’re in.

Oh, yeah.So we’ve logged in as the user.

Mitch so we can see what’s in here.

We can see that there is a user file.

So this is not a nice shell.

We don’t have auto correct with tabbing,but we can look at this flag.

So there’s a list of things that we shoulddo in here, which I don’t know how to do.

Just common checks, one that I do know how

to do and that it’s sortof hinting towards here.

If we just want to list out the homedirectory,

every user is going to have a homedirectory that should and we can see

that there indeed is another userand it’s saying here, what’s their name?

So we have another user.

So what can you leverageto smarter privilege shell?

This is where I got, again, not so simple.

This was a bit tricky.

After a little bit of cheating,

I did find that the way to do this is runpseudo l, which is going to go and tell us

anything that we can runwith pseudo privileges.

So if we go and run pseudovim,which is a text editor,

which I do not use because I do notunderstand it, but maybe one day I will.

And we run colon explanation mark bash.

This is going to spawn a bash shell,but since we can run it as

root privileges, that will automaticallygive us these root privileges.

Now, I went down a wrong turn.

At this point, I didn’t actually do this.

I was looking into logging back in asthe other user through SSH,

and I found her password because I openedactually, I thought it was really smart.

I openedthe password file and I got the hash from

the shadow file ratheranyway, it didn’t work.

This is how you do it be okay to makemistakes as we go through our learning.

Anyway, so now we can just go and LS our

root directory and we should see a routeand we can just go ahead and get that.

And that is our all right, sorry.

Vim was how we did that.

And then we’ve just found our last flag,

which is how we go through itthat way and we get to the end.

So I hope you enjoyed that was fun.

It was a lot easier doingit retrospectively.

Cannot tell you how frustratingthis was, but it’s learning.

I’m actually getting better at it beingless frustrating and more appreciating.

The journey that is learning.

Cybersecurity.

It’s okay when things do geta bit frustrated, but yeah.

So, like, that whole Python Two

to Python Three things that trippedme out heaps, it was annoying.

What used to frustrate me with this sort

of thing is like, oh,everything should be perfect.

Like, these are the makersand the writers of the CTF.

They should everything perfect becausein education, everything needs to be like

but technology justdoesn’t work like that.

I think this CTF was made in 2019.

I’m pretty sure Python Threewas around for a while.

But this exploit that he chose to use,that CBE, the maker of that exploit,

could have made that Python file ages agoand Python Three wasn’t even a thing.

Should the creator of the roomhave picked another CBE to use?

One that’s a bit newer?

But this is a common thing that peopledon’t update their applications and you

might find an exploit that’srunning on Python Two.

So knowing how to, as we learn after a bit

of trial and error,to change our Python files from two

to three, isn’t that in itself likea good lesson, something to learn?

It’s not even outlinedin the room anywhere.

But yet now we’ve got another skillunder the belt that we can use.

This is sort of how I’m looking atdoing more when we are learning.

This is just better,

sort of accepting that technology isnever going to be that straightforward.

And every time we get frustrated

in the learning journey, just to,I don’t know, sort of take it for what it

is and we will eventually use thissomewhere and it will be helpful.

I don’t think 100% of the trial and erroris always going to be useful, but

I think this is especially goingto be useful in some future.

So it’s still worth doing because you

might get some usefulness out of it,even though you still might not.

Anyway, guys, that is the simpleCTF from Try hack me.

I hope you enjoyed this.

A full written right up will bein the link below if you prefer to go

through that with screenshotsand explanations.

If you enjoyed this video,please do leave a like and subscribe.

Appreciate your feedback.

It honestly does help.

If anything,it’s very much a mental health.

Seeing comments and stuff is good

motivation, so I genuinely doappreciate that sort of thing.

If you have any feedback or how I could

improve, I’m always open for improvement,so please do that.

Otherwise yeah, I’m going to stoprambling and see you in the next one.

Hey, I know that the video is over.

But if you stuck around this long,you’re a legend for one.

And for two, just apologies.

There’s actually a lotof sniffles and coughs.

And I say so much,just want to apologize for all that.

If you are in this video,you deserve that much at this stage.

Okay?Thank you.

Sorry.

</div><div class="hs-embed" data-hide_video="true" data-id="cf0f9007980c47a2bdb42aee378367de" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Hints

- How many services are running under port 1000? `nmap`
- What is running on the higher port? Check the `nmap` scan results.
- What’s the CVE you’re using against the application? `CVE-****-****` don’t forget to include `CVE-` at the beginning.
- To what kind of vulnerability is the application vulnerable? `***i` something injection…?
- What’s the password? `hashcat <hash> <wordlist>.txt`
- Where can you log in with the details obtained? Check your `nmap` results again.
- What’s the user flag? `ls` and `cat` what you find.
- Is there any other user in the home directory? What’s its name? `cat /home/`
- What can you leverage to spawn a privileged shell? Check what can be run with `sudo -*`.
- What’s the root flag? `cat /root/root.txt`

<div class="elementor elementor-5483" data-elementor-id="5483" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-32d8c94 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="32d8c94" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-5e7c56e" data-element_type="column" data-id="5e7c56e"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-fc64076 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="fc64076" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-f7d6b37" data-element_type="column" data-id="f7d6b37"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-4c75247 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="4c75247" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Recent Posts

 </div> </div> </div><div class="elementor-element elementor-element-322ad34 elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="322ad34" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">How To Fix TryHackMe VPN Not Working | Troubleshooting OpenVPN</span> </div> ](https://mrash.co/how-to-fix-tryhackme-vpn-not-working-troubleshooting-openvpn/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Crack The Hash TryHackMe Walkthrough</span> </div> ](https://mrash.co/crack-the-hash-tryhackme-walkthrough/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section> <section class="elementor-section elementor-inner-section elementor-element elementor-element-d91d33b elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="d91d33b" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-no"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-6dee180" data-element_type="column" data-id="6dee180"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-7acfc36 elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="7acfc36" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">Popular Posts

 </div> </div> </div><div class="elementor-element elementor-element-7b9396d elementor-widget elementor-widget-elementskit-post-list" data-element_type="widget" data-id="7b9396d" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="elementskit-post-list.default"><div class="elementor-widget-container"><div class="ekit-wid-con">- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">OneNote to Notion - Moving Apps</span> </div> ](https://mrash.co/onenote-to-notion-moving-apps/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">100 Days Of Hacking</span> </div> ](https://mrash.co/100daysofhacking/)
- [ <span class="elementor-icon-list-icon">  </span><div class="ekit_post_list_content_wraper"> <span class="elementor-icon-list-text">Hackers Learning Path</span> </div> ](https://mrash.co/learning-path-for-beginner-hacker/)
 
 </div> </div> </div> </div> </div> </div> </div> </div> </section><div class="elementor-element elementor-element-2763e2a elementor-widget elementor-widget-text-editor" data-element_type="widget" data-id="2763e2a" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="text-editor.default"><div class="elementor-widget-container"><div class="elementor-text-editor elementor-clearfix">\*Shamless self-promotion, I know.

 </div> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div>## Steps

1. Enumeration as always, start with `nmap -vv -A <ip>`. With ports 21, 80, and 2222 open, we can see what we can find logging into ftp via anonymous via `ftp <ip>`. I didn’t find anything but checking out other writeups, it looks like my THM VM didn’t work as intended. ![https://p146.p4.n0.cdn.getcloudapp.com/items/v1uOL784/7113721d-e1e0-4831-9ae8-91efb0d1b77c.jpeg?v=4538363f6feb6a7e24f0c9dc88a2ee9c](https://p146.p4.n0.cdn.getcloudapp.com/items/v1uOL784/7113721d-e1e0-4831-9ae8-91efb0d1b77c.jpeg?v=4538363f6feb6a7e24f0c9dc88a2ee9c)
2. More enumeration, since we have a website, let’s navigate to `http://<ip>` and see what we can find. After manually searching, not a lot there, let’s use `dirsearch -u http://<ip>` to find `/simple/` directory. Navigating to `http://<ip>/simple`, we can find a system called ‘CMS Made Simple’ or CMSMS for short. Find the exploit using `locate 'php/webapps/*****.py'`, then make a copy using `cp /usr/share/exploitdb/exploits/php/webapps/*****.py .` ![https://p146.p4.n0.cdn.getcloudapp.com/items/RBumyjpZ/8fbe854c-6f61-4e58-9574-7bd77b8ee8eb.jpeg?v=2a6edc2faadc68365fbfd0cdfc500b11](https://p146.p4.n0.cdn.getcloudapp.com/items/RBumyjpZ/8fbe854c-6f61-4e58-9574-7bd77b8ee8eb.jpeg?v=2a6edc2faadc68365fbfd0cdfc500b11) ![https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGR9J/330665a7-bbf1-41c6-b102-bfdea8d214ec.jpeg?v=5d0cc838a21d5e50239766e7e0c4880f](https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGR9J/330665a7-bbf1-41c6-b102-bfdea8d214ec.jpeg?v=5d0cc838a21d5e50239766e7e0c4880f) ![https://p146.p4.n0.cdn.getcloudapp.com/items/6quzEl4d/6aeb90bd-4b8e-44da-8452-d2bbd49a2c36.jpeg?v=e0e0ab85aa0e87cf6188cc57314fc9e3](https://p146.p4.n0.cdn.getcloudapp.com/items/6quzEl4d/6aeb90bd-4b8e-44da-8452-d2bbd49a2c36.jpeg?v=e0e0ab85aa0e87cf6188cc57314fc9e3)
3. Getting the exploit working, now, this took a bit of time and this makes me call it ‘Not So SimpleCTF’… the correct CVE exploit is written in Python 2 with missing modules that are working in Python3. To fix this, run `sudo apt install 2to3`, then `2to3 *****.py`, this will convert the exploit from Python 2 to Python 3. ![https://p146.p4.n0.cdn.getcloudapp.com/items/NQulx00O/e0a7b30d-5ba9-4988-b248-1388071276d6.jpeg?v=1a05e098109581641687f3ac5598d3bc](https://p146.p4.n0.cdn.getcloudapp.com/items/NQulx00O/e0a7b30d-5ba9-4988-b248-1388071276d6.jpeg?v=1a05e098109581641687f3ac5598d3bc) ![https://p146.p4.n0.cdn.getcloudapp.com/items/4gurZqq9/4459e9cc-f33c-4e45-bd71-0043678129ff.jpeg?v=c26cf4059e2adb43c82ec2f0c4fc3073](https://p146.p4.n0.cdn.getcloudapp.com/items/4gurZqq9/4459e9cc-f33c-4e45-bd71-0043678129ff.jpeg?v=c26cf4059e2adb43c82ec2f0c4fc3073)
4. Using the exploit by running `python *****.py -u http://<ip>/simple`, note this took me twice to get the correct results. I tried a third time and the resulted varied, so you are warned, try a few times to make sure you get consistent results. ![https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGRRv/47ebc687-d013-4c8b-935b-c88e4bfe4f66.jpeg?v=b72d7237c17451d2db2c0bdd83bd3d96](https://p146.p4.n0.cdn.getcloudapp.com/items/JruoGRRv/47ebc687-d013-4c8b-935b-c88e4bfe4f66.jpeg?v=b72d7237c17451d2db2c0bdd83bd3d96) ![https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2](https://p146.p4.n0.cdn.getcloudapp.com/items/kpu8428g/d56f6ace-eb3e-43e5-a402-490dbc1ff3bb.jpeg?v=c6572056b97da622ef551af4c6e6eae2)
5. Crack the password, use `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`. To explain, `-m 20` sets `hashcat` to `md5` with `salt:hash` which is perfect from the exploit we ran. ![https://p146.p4.n0.cdn.getcloudapp.com/items/L1uXWAAW/fa83ac46-712b-4f91-a726-fac1096fd944.jpeg?v=920a291fba73ca19b65152880a8867bf](https://p146.p4.n0.cdn.getcloudapp.com/items/L1uXWAAW/fa83ac46-712b-4f91-a726-fac1096fd944.jpeg?v=920a291fba73ca19b65152880a8867bf)
6. Access via `ssh`, run `ssh mitch@10.10.44.147 -p 2222`, don’t forget to specify the port number from the earlier `nmap` scan. ![https://p146.p4.n0.cdn.getcloudapp.com/items/DOudmZZr/ddd4e2be-e6c2-4283-971a-62f187630d4f.jpeg?v=0adb7d12cdaa4dab850c89953d81dc60](https://p146.p4.n0.cdn.getcloudapp.com/items/DOudmZZr/ddd4e2be-e6c2-4283-971a-62f187630d4f.jpeg?v=0adb7d12cdaa4dab850c89953d81dc60)
7. Lastly, escalate privileges, now like other steps, this isn’t so simple either, but do your best to not cheat and search around. I’ll give you a hint, you can use a certain text editor as `sudo` which can spawn a bash shell with `:!bash`. ![https://p146.p4.n0.cdn.getcloudapp.com/items/p9uOXJJ2/9bdd5af5-1810-4116-9ec7-10a6d2ac4788.jpeg?v=853151cc53a27778e2160ff0207ee930](https://p146.p4.n0.cdn.getcloudapp.com/items/p9uOXJJ2/9bdd5af5-1810-4116-9ec7-10a6d2ac4788.jpeg?v=853151cc53a27778e2160ff0207ee930)

## Reflection

This was a fun CTF from [MrSeth6797](https://tryhackme.com/p/MrSeth6797) ([Twitter](https://twitter.com/0xSeth), [Website](https://floreaiulianpfa.com/), [Writeup](https://floreaiulianpfa.com/simple-ctf/)), I would recommend this to any fellow hacking beginner. I think the basics are always important, this reinforced the importance of searching for known vulns and exploits. And also how exploits can be a bit finicky, like needing to convert the exploit from Python 2 to 3.

I use to get a bit annoyed by rooms like this, where it wasn’t clear with things like this. But after a bit more learning, this is how technology is. Things change, the creator of that exploit wrote it in Python 2, I assume at the time Python 3 wasn’t around. So fast forward to now, our Linux systems have both Python 2 and 3, but modules might only work with 3, not 2.

So yeah, all these sorts of issues become less frustrating the more I learn, and it just becomes a part of the process. I’m also leaning into writeups and the THM Discord more and more. I’ve spent too long banging my head against the wall and going off track. It’s all a part of learning, but writeups can be used in a way that you don’t need to see all the answers, scrolling is a thing.

SimpleCTF is a good, solid CTF from THM, like I said, not so Simple, but in the end, it’s worthwhile. This is day 51 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on my [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking/coding/learning.

## Notes

openvpn issues, in folder w/ ovpn file

```
<pre class="wp-block-code">```
sed -i 's/cipher AES-256-CBC/data-ciphers AES-256-CBC/' *.ovpn

```
```

nmap scan: `nmap -vv -A <ip>`

```
<pre class="wp-block-code">```
Completed NSE at 17:35, 0.00s elapsed
Nmap scan report for 10.10.138.218
Host is up, received syn-ack (0.29s latency).
Scanned at 2022-07-02 17:34:56 EDT for 56s
Not shown: 997 filtered tcp ports (no-response)
PORT     STATE SERVICE REASON  VERSION
21/tcp   open  ftp     syn-ack vsftpd 3.0.3
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.4.33.98
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
80/tcp   open  http    syn-ack Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 2 disallowed entries 
|_/ /openemr-5_0_1_3 
|_http-title: Apache2 Ubuntu Default Page: It works
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
2222/tcp open  ssh     syn-ack OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 29:42:69:14:9e:ca:d9:17:98:8c:27:72:3a:cd:a9:23 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCj5RwZ5K4QU12jUD81IxGPdEmWFigjRwFNM2pVBCiIPWiMb+R82pdw5dQPFY0JjjicSysFN3pl8ea2L8acocd/7zWke6ce50tpHaDs8OdBYLfpkh+OzAsDwVWSslgKQ7rbi/ck1FF1LIgY7UQdo5FWiTMap7vFnsT/WHL3HcG5Q+el4glnO4xfMMvbRar5WZd4N0ZmcwORyXrEKvulWTOBLcoMGui95Xy7XKCkvpS9RCpJgsuNZ/oau9cdRs0gDoDLTW4S7OI9Nl5obm433k+7YwFeoLnuZnCzegEhgq/bpMo+fXTb/4ILI5bJHJQItH2Ae26iMhJjlFsMqQw0FzLf
|   256 9b:d1:65:07:51:08:00:61:98:de:95:ed:3a:e3:81:1c (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBM6Q8K/lDR5QuGRzgfrQSDPYBEBcJ+/2YolisuiGuNIF+1FPOweJy9esTtstZkG3LPhwRDggCp4BP+Gmc92I3eY=
|   256 12:65:1b:61:cf:4d:e5:75:fe:f4:e8:d4:6e:10:2a:f6 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJ2I73yryK/Q6UFyvBBMUJEfznlIdBXfnrEqQ3lWdymK
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.

```
```

dirsearch: `dirsearch -u http://<ip>`

```
<pre class="wp-block-code">```
dirsearch -u <http://10.10.138.218>

  _|. _ _  _  _  _ _|_    v0.4.2
 (_||| _) (/_(_|| (_| )

Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 30 | Wordlist size: 10927

Output File: /home/kali/.dirsearch/reports/10.10.138.218/_22-07-02_18-08-57.txt

Error Log: /home/kali/.dirsearch/logs/errors-22-07-02_18-08-57.log

Target: <http://10.10.138.218/>

[18:08:58] Starting: 
[18:09:09] 403 -  299B  - /.ht_wsr.txt                                     
[18:09:09] 403 -  302B  - /.htaccess.bak1
[18:09:09] 403 -  304B  - /.htaccess.sample
[18:09:09] 403 -  302B  - /.htaccess.orig
[18:09:09] 403 -  302B  - /.htaccess.save
[18:09:09] 403 -  303B  - /.htaccess_extra
[18:09:09] 403 -  302B  - /.htaccess_orig
[18:09:09] 403 -  300B  - /.htaccess_sc
[18:09:09] 403 -  300B  - /.htaccessBAK
[18:09:09] 403 -  300B  - /.htaccessOLD
[18:09:09] 403 -  301B  - /.htaccessOLD2
[18:09:09] 403 -  292B  - /.htm                                            
[18:09:09] 403 -  293B  - /.html
[18:09:09] 403 -  302B  - /.htpasswd_test
[18:09:09] 403 -  298B  - /.htpasswds
[18:09:09] 403 -  299B  - /.httr-oauth
[18:09:12] 403 -  292B  - /.php                                            
[18:10:12] 200 -   11KB - /index.html                                       
[18:10:34] 200 -  929B  - /robots.txt                                       
[18:10:35] 403 -  301B  - /server-status                                    
[18:10:35] 403 -  302B  - /server-status/                                   
**[18:10:37] 301 -  315B  - /simple  ->  <http://10.10.138.218/simple/**>         
                                                                             
Task Completed

```
```

Find CVE: `searchsploit ‘CMS Made Simple’`

```
<pre class="wp-block-code">```
CMS Made Simple < 2.2.10 - SQL Injection | php/webapps/*****.py

```
```

Find local CVE file: `locate 'php/webapps/*****.py'`

```
<pre class="wp-block-code">```
/usr/share/exploitdb/exploits/php/webapps/*****.py

```
```

[🔗 CVE](https://www.exploit-db.com/exploits/46635)

Using CVE:

- Ran `sudo apt install 2to3` – exploit written in `python2` has missing modules.
- `2to3 *****.py`, `python *****.py -u http://<ip>/simple` Note, tried multiple times and then randomly worked… didn’t change anything, ghost in shell moment.
- Also, took two attempts to get correct salt and hash, third attempt again produced different set.

```
<pre class="wp-block-code">```
[+] Salt for password found: *****
[+] Username found: *****
[+] Email found: *****
[+] Password found: *****

```
```

Crack Password: `hashcat -O -a 0 -m 20 '<salt>:<hash>' <wordlist>.txt --show`

- Note, salt first, then hashed password, used hint for wordlist.

Connect: `ssh *****@<ip> -p 2222`

PrivEsc: `sudo -*`

```
<pre class="wp-block-code">```
User mitch may run the following commands on Machine:
    (root) NOPASSWD: /usr/bin/*******

```
```

Escalate shell: `sudo ***`, `:!bash`, `cat /root/root.txt`

Thanks for reading and I hope you learned something from this little exercise. This is day 52 of [\#100DaysOfHacking](https://mrashleyball.com/100daysofhacking/) on the [Hackers Learning Path](https://mrashleyball.com/learning-path-for-beginner-hacker/). [Subscribe](https://go.mrash.co/newsletter) for [CyberSec](https://mrashleyball.com/starting-out-in-cyber-security/) updates or [read](https://mrashleyball.com/blog) more, happy hacking.