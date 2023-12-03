---
title: Network Services 2 TryHackMe Part 1 NFS
url: thm-nfs-1
alias: network-services-2-tryhackme-part-1-nfs
# image: https://www.youtube.com/watch?v=lBWxgGQObuo
type: Post
categories: Post 
draft: true
---

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/lBWxgGQObuo?feature=oembed" title="Network Services 2 TryHackMe Part 1 NFS" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:600px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ Network Services 2 TryHackMe Part 1 NFS](https://www.happyscribe.com/?utm_source=embed-player&utm_term=72e624b2836b40ad8f26e458c5fb59e7 "Network Services 2 TryHackMe Part 1 NFS")

Hello, welcome back.

We are doing some more Trihack me

walkthroughs and it’s goingto be Network services too.

Put my phone on silent orat least turn it down.

Today we’re going to be doing this roomand it reads enumerating and exploiting

the more common networkservices and misconfigs.

If you want to catch Network services one

there will be a card popping up or a linkdescription in the description or

something, or ratherwe will be going through the tasks

together and you’re more thanwelcome to follow along.

If you pick anything up that I’ve done

wrong or something,please reach out, let me know.

Go let you know that there isa written write up below too.

So if you want to just scroll throughto see any particular areas that will be

there but yeah, if you wantto subscribe that’d be cool.

Otherwise no pressure.

No pressure.Cool.

So let’s get started with task one,

get connected and we’llread this through together.

I do this, I sort of like skim areasand then when I miss things I go back.

So if you want to pause and read in moredetail, of course you can do that.

Before I go, I’m just going to hit

the start machine on task three becausewe’ll be focusing, this is part one.

So we’ll be doing NFS.

So tasks one to four in this video.

Okay, with that all out of the way,let’s get into it.

So we’ve got task one, get connected.Hello and welcome.

This room is a sequel for the firstNetwork Service room which was great.

Similarly it will explore a few morecommon network services,

vulnerabilities and misconfigs that we’relikely to find in CTF and Pen tests.

So that’s cool.So yeah, pretty much we need that.

Also we need to do Linux fundamentalsif you haven’t done that.

Also got some walkthroughs if you’d want.

Otherwise go back,

make sure we’re connected on the Open VPNso you can always test by pinging

ten and if you’re on the networkyou will get some back.

Awesome.

So there’s also a little bit aboutthis not being a WiFi hacking room.

Okay, I should do that one though,it’s going to come up a couple of times.

Cool.Got our IP there.

I’m just going to quicklytry and ping that.

Cool, boxes up.Awesome.

So NFS stands for Network File System

and allows a system to share directoriesand files with others over a network.

By using NFS, users and programs can

access files on remote systemsalmost as if they were local files.

It does this by mounting all ora portion of a file system on a server.

The portion of the file system that ismounting can be accessed by clients

with whatever privilegesare assigned to each file.

I’m used to manifest in Windows

environments from where I’ve worked,but it’s cool learning about it in a Linux

environment too and howthat they can both do it.

So how does it work?

We don’t need to understand a technical

exchange too much to beable to exploit it.

However, this is somethingthat interests you.

There is a link herethat I will read one day.

First the client I will request amount

directory from the remote host and a localdirectory just the same way as like

a physical device like plugginga USB or a hard driver’s line.

The mount service then will actto connect to the relevant mount damian.

I don’t know how we say this using RPC.

So another protocol

the server checks if the user haspermissions to mount whatever directory

has been requested it will return a filehandle which uniquely identifies each file

and directory that is on the surfaceI’m getting the sense of things.

RPC calls place the Nfsd,the NFS damian or Damon on the server.

This calls and takes the file handle

the name of the file to be accessed,the user’s user ID and the group’s ID.

So checking its permissions,

these are used determiningthe access rights or permissions.

This is what control user permissions ie.

Read and writer files.

So what runs it?

Using the protocol we can transferfiles between computers and Windows.

Other non Windows OS like Linux Mac.

And it’s pretty universal.

I honestly always thought that this wasjust purely for Windows

because isn’t a computer running windowsserver can act as an NFS server

clients likewise NFS allowedWindows based computers.

So yeah, it can go either way.

I thought the whole new file thing wasa Windows thing, but this is network file

system but I associateit with the new files.

I get that mixed up.

So they’re different here Samoor sir,

I’ve got all this linked off that Iwill I promise I will read it again.

So let’s go throughthe questions together.

We’ve got what does NFS stand for?

Network file system.

I’ve got such a bad memory.

What process allows an NFS clientto interact with a remote directory as

through as though itwas a physical device.

What process allows ourNFS client the process?

What was the process we had back up here?

Mounting are we calling it?

I think mounting?

Yeah,caviar I have done this but it was

a little bit ago so Idon’t remember everything.

I remember some things.

So there might be typical bit of problem

solving and going back over and reading reremembering to what does NFS use

to represent filesand directories on the server?

Good question.What does it use to represent files?

Uses the file handle.

Is that one what are you looking for?Two words?

Yeah, I think it’s the file handle.

It’s one that says this is the thing

that it uses to connectbut I think it uses the file handle.

We had a hint.What does the operating user says?

Yeah, mounting.

Cool.

What protocol does NFS use to communicatebetween the server and the client.

So there was another protocol

that it specified in some PC.

Awesome.

What two pieces of user data does the NFS

server take as parametersfor controlling user permissions?

Format?Parameter one and parameter two.

So something.

So under the file handle we gotthe name of the file to be accessed.

We’ve got the user, so we gotthe user ID and group ID.

I’m pretty sure.

Now I remember.

Can a windows NFS chef file with a linux?

You can if we remember up here itsaid that it can go either way.

So what runs it?

Everything can run it one wayand everything can run the other way.

So the next kind of Linux yeah,Linux can share files with macOS clients.

Everybody’s happy.

What’s the latest version of NFS released?

So I don’t know.

Let’s have a look.

Network file system for NFS.

So we got V two, we gotV three, we got V four.

So I’m going to take it v four being

the largest number and not seeinganything else by just scanning around.

Version four came out December 2000.

We got 4.1 2010 and we got 4.2

from 2016 and it does say since 2016.

So as of 2020 there’s nothing new so far.

But being 2022, maybe theremight be something new.

How long was it?Between six years.

So maybe we got to wait a few more years.Cool.

So that’s going to be our understanding.

NFS.

So we’ll close that one.

So let’s go over to task three for NFS.

And we’ve already started our machine,

we already pinged it,so we should be good to go.

So before I go and read this,I know we do have to go ahead and do

a port scan, so it’s going to tellus about mounting and shares.

So what I’m going to do is I’m going

to run the port scan,then I’m going to do a bit of reading,

going to let that run in the backgroundand maybe by the time we finish reading

it’ll all be done, otherwiseI’ll just skip the video.

So let’s go and do an Nmap against our

machine that is not our machine,that is the version of anniversary.

But we’re going to do a coupleof switches like always.

Double VV forbos I’m goingto make sure I do a couple A.

I’m actually going to just do this.

This was from last scan,

so if you want to go ahead and copythat or you’ve already got it.

I’ve gone ahead and actually createda network services two directory.

So I’m going to

output to a Scanport file and justhave a scan port back up just in case.

But the thing we do want to change,that’s not how terminals work actually.

We do want to just make surewe put in our IP in there.

So if you’re unfamiliar with the switches,that’s all good.

I’m learning two this was the all or

aggressive mode, which is going to tryand detect and run some scripts.

I think this is thengoing to run all ports.

So we’re trying to scan as many ports as

we can and get as muchinformation as we can.

And this is just outputting the file.

Cool, that should be cool.

So going to let that run.

Already found a couple of ports,so that’s very exciting.

So while that’s running in the background,let’s keep on going with what we got here.

All right, before we begin,

make sure to ploy the roomand give it some time to boot.

Yeah, it’s been booting for a while.Please.

This can take up to five minutes,so yeah, we’re good.

What is enumeration?

Enumeration is defined as a process,

establishes activeconnection to the target host to discover

potential attack vectorsin the system and blah, blah, blah.

Finding out stuff that’s probably a goodlink to use for blogging and stuff.

Cool.

So we’re going to findout stuff requirements.

In order to do more advanced enumeration

on NFS servers, we’regoing to use and shares.

We’re going to need a few tools.

So for this we have NFS common.Do I have?

NFS common.

I don’t believe I do.

So let’s just try an Apt.

Cool.

So it’s a package on the list,so let that do its thing.

It’s important to include shadow mount FC.

And let me use this shadow mount.

These are going to be useful tools when it

comes to extracting informationfrom Fchat.

If you like more informationabout this, please go here.

I’m all good.

You can install this by running aptinstall and it’s con, which we just did.

It’s part of the defaultrepositories from Linux distro.

That makes it easy.

Not that I don’t like installing differentthings from like GitHub and stuff, I mean,

it’s like fine, but it is nice whenthings are just like on your system.

I’m just going to run a quick abt.

What?

This keeps happening.I don’t know what is up.

See my terminal right now,I’m just going over.

I’m just going to runa quick update and upgrade.

Seriously, what is with thisterminal thing?

Okay, port scanning covered many times

before when you use Nmap,first up is port scan.

So anything else that weneed to know here?

You can do this.Just Nmap.

We use that NP for allthe ports mounting shares.

Your client system needs a directory where

content can be shared betweenthe house and the server.

So once we’re finished with our Nmap scan,

which is going to take a little while,we’re going to use mount Tmfsip.

So we’ll put our IP there and then share

and we’ll put it in our temp fileand create a mount and use a flag.

No locks.So that runs it as root.

Execute the mount command.

Which I assume is part of NFS common.

Or maybe not type of device to mountso T to specify the device type.

IP.The address of the NFS server.

And the name of the share.

So Share isn’t like a flag, this isjust a name, which could be anything.

In this case it’s just Share.Cool.

And no lock specifiesnot to use NLM locking.

So I have no idea what NLM locking is.

Network lock manager, purpose ofversion two and three.

This protocol is closelytied with NFS protocol.

Self shares handle fire.

Cool.

I now have still no idea what it is,but we don’t want it.

Good.

Okay, so now we understand our tools.

Conduct a thorough port,

scan all of your choosing and we wantto find out how many ports are open.

So out of the top thousand or so,

we do have two and we arelooking for a one digit answer.

This is a bit of a worry.

This is like what gets me.

Like, I don’t know if this isthe switch that makes it go longer.

You know what,

I’m going to undo it and I’m goingto use the T four to speed it up.

Okay, so you don’t have to wait through.

I’m going to skip ahead,but I’m going to run that.

And so our skin has finished.

Took little less time that we speed it up,

but it has tried to find a littlebit more about the ports.

So let’s go over the first question again.

Conduct a third.

How many ports are open?

So we’ve got one.Instead of counting them,

I’m going to try and do somethingthat I saw in another one.

We can just cut out the file that I

created, but we’ll justgrab anything that is open.

Cool.So a little bit easier.

123-4567 ports are open,so let’s just have a little bit.

So we’ve got SSH, we’ve got RPC binds.

So RPC was another protocol that NFS uses.

So it looks like they’reall got RPC or something.

We’ve got mount D on a couple of ports.

So not sure if these are like all the one

service and they just have multiple portsto use, or these are definitely different

services, thereforeneeding different ports.

No.

So which port contains the servicewe’re looking to enumerate?

So this is a bit tricky.

I’m assuming it’s goingto be one of these.

We’re looking for four digits.

It’s telling me that this is definitelythe one that actually says NFS,

so I’m going to just copy overthat number and put it in.

Cool, so that’s what we’re looking at.

If that wasn’t here, honestly,I wouldn’t be 100% sure.

I mean it does say NFS,but otherwise fair game.

Now use the user bin SMSHIe to list the NFS shares.

Okay, let’s try that.

So is show mounts.

Yes, it’s in the binary,so we can just run it as is

e, and then our IP address,which I will just copy over and let’s see

if that takes on so exportlist from this is under home.

Is that right or is that it?

Have I misunderstood that?

Home is literally it?

What is the name of the visible share?

Oh, that is it.That tripped me out.

I thought it was exporting a list to thisdirectory, but home is actually it.

Okay, cool.That’s cool.

All right, time to mountthe share to our local machine.

Let’s make the directory so make do.

And we’re putting this in our temporaryfolder with an absolute path.

I was going to create this mounting folderhere

so we can just list out everything elsein our temporary folder or directory.

Got a bunch of random stuff.

And then we’ve got ourmount that we just created.

Then we want to use the mount command webroke down earlier to

NFS share to the local machine changedirectory to where you mounted the share.

What is the name of the folder inside?

Okay, let’s go up NR and use this.

So we’re going to use the mount command.

Now, if you’re wondering,I don’t need pseudo privileges because I’m

already logged in as my most privilegeduser, so I don’t have to use that.

But when you use P for the type which was

NFS, then we’re going to paste in ourIP again, which I need to copy.

Thank you.Try hack me for putting it right there.

And then we’re going to put in the share.

So this share that we’reconnecting to is home.

That was the file that I saw.

Now, I don’t think weneed to put a file path.

I don’t think we need to do that.

Could be wrong.

Let’s see.

And then we’re going to put the locationof where we’re connecting this share to.

And then that last one, no lock,

which does the thing aboutthe thing that’s it cool.

See what it does.

So if it is working, it is going outand grabbing it and connecting it.

So if there’s a little bit of time delay,that’s not a bad thing.

So let’s list out what is in our temporary

and in that mount directoryand hopefully we see something great.

So that’s successful.

That means it’s worked, basically.

All right, let’s look inside this.

So you’re going to hit the up arrow

and we’re going to spell it outand hit tab and see what we’ve got.

So I can’t see anything,

but that doesn’t meanthere’s nothing there.

Let’s use Ll, which is shorthand for list.

Okay, I really don’t have anything there.

Looks like we’re inside a user’s home.

Okay, interesting.Let’s do a bit of research.

Now let’s have a look through the folders.

Which of these folders contain the keys?

Did I do something wrong?

Because I can’t actuallysee anything in this.

I may have to retrace my steps ifI have done something wrong here.

Cool.

I’m just silly because Ll doesn’tinclude the dasha I thought it did.

It only does the L, which it lists out.

But A includes all,which shows us all the files,

including hidden files,which has the period before it.

So there’s a little hint in here.

They bolded the letters RSA,which is the acronym for our RSA files.

So there’s the RSA public keysand private keys, which is for SSH.

So if we list out lain here, but then we go SSH this time

and we look inside that file,then we can see those files.

So this is what we’re after,RSA, public and private.

So SSH, that’s wherewe’re looking inside of.

And then what are the keys?

That’s mostly useful.

So out of these two,this one is the private key.

So PU B, for public, but IDA is almost

because that’s private,you shouldn’t be able to see this.

Cool.So copy this file to a different location.

Cool.So we can use the CP command to copy that.

So in that temporary file in the mount,

in the cappuccino and then in the SSH,and we’re going to grab that.

What am I doing?ID.

Yeah.

So there’s just a little bit of delaybetween my keyboard and then server.

So we’re just going to copythat and go to space.

And I’m just going to put it

in the directory that I’m already at,which is in the network services.

So cool.So I’ve grabbed that.

So we can list out here.

So here it is.

So we’re going to bechanging the permissions.

So we’re going to be using the 600.

So that means I think it’s read,testing my permission knowledge.

So let’s just run 600 against it.

So we can see here we’ve got read,write, and then for the user.

So no execute and nothing for the groupand nothing for everyone else.

So we’re changing it.

I’m going to put myself on a limb and I’m

going to say the W is goingto disappear after we run this.

See if I’m right.

I am totally ready to be wrong.

I am totally wrong.

It was the same, I thoughtit’s already at 600, which seems weird.

I don’t know if I’m probablyjust getting confused.

I don’t know.I don’t know.

Assuming we have the word right about what

type of directory this is,we can pretty easily work out the name

of the user the key corresponds to,which is going to probably be cappuccino.

So this way we’re going to SSH,

use the I to import thisfile as our authentication.

So let’s see if that works.

So SSH, we’re going to use the idrsa file,we’re going to use the cap.

How do you spell cappuccino again?

C.

Cool.Going to punch that in.

Are you sure you want to do this?Yes, please.

Warning, it’s pinned host.

And that just loads usin because that’s our password.

Awesome.So can we log in using that?

Yeah.

Okay.

I’m just trying to remember 600, I thinkfour was breed, seven was everything.

Six, I can’t remember my bid sets,whatever.

Cool.Anyway, we’re in.

So who am I?

I’m running cappuccino.

I would be in the directory.

So let’s list out the home.

And there’s only one other useron this system besides Root.

So we’re going to try and proveescalate up the privileges tree.

Vertically, of course.

Let’s go over to task four.

So we do have our foothold in the system,which is cool, but we want to go to Roots.

So just going to quickly scroll down.

We need to gain definitely Prove esque.

All right, we’re done, right?

Not quite.

We have a low privilege shell,so we can’t do much with this user.

So you might be able to use escalate

privileges dependingon how it’s configured.

What is root squash?

What is root squash on NFS shares?

Root squashing is enabled and prevents

anyone connecting to the NFS share fromhaving root access to the NFS volume.

Remote root users areassigned as user NFS.

Nobody when connected,which has the least local privileges.

Not what we want.

However, if this is turned off, it canallow the creation of SUID bid files.

So this is special user IDs or something?

I can’t remember exactly.

But like, temporary privileges, I think,

allowing a remote user routeaccess to connect to the system.

So what are the SUID fits?

That essentially this means that the file

or files can be run with permissionsof the files owner or group.

In that case, as a super user,

we can leverage this to geta shell with the privileges.

There’s, like, this really long command

that you can just copy paste to seeall of these files on a system.

Apparently, it’s, like,common in CTS and stuff.

Okay.

Method sounds complicated,but really provide you familiar with it?

I’m not that familiar with how it works.

It is complicated for me, but whatever.

It’s fairly easy to understand.

We’re able to upload files to their names,

share, and then controlthe permissions of these files.

We can set the permissions of whatever we

uploaded in the caseof a Bash l executable.

Okay, please walk me through this becauseI’ve gone through this room and I’ve done

this a couple of times, but it’s stilllike yeah, it takes me a little bit.

Anyway, due to compatibilityreasons will be standard.

You can download it here.

Will this be straight up download?

Okay, so this is just for this file.

Can I just go to the raw

view raw upload the bash.

Can I just use Wget on the system?

Can I get and just download that file?

Probably not, right?

It probably doesn’t have outbound traffic.

Okay, so in that case,we can just W, get this.

Man, I love this sick terminal.

I’m going to go over here.

Let me just change directoriesover into documents.

Try hack me networkservices, too.

Cool.So we got Bash roar true.

All right, let me just try this again

and ll but just call it Bash.

Does that work?

No, I got fine, I’ll just move sorry.

This is probably I wasgoing to call this bash.

Cool.

So if we just cut out bash,

this should be in binary,so it doesn’t make a lot of sense.

All right, cool.Got that.

So we do need to getthis over to the system.

So we can do this by a couple of ways.

I’m going to start a Python server

on here using Python three Mhdcpserver running on port 8000.

So if we tell our system to download

from our local IP so we’re goingto go back over to capture.

Did I lose my mouse?Again.

Sometimes my mouse juststops working here.

Okay, so you definitely can’t,

but we can w get locallyto this system running on port 8000.

So that’s my system.

I just started a web server,and we’re just going to download bash.

I’m just going to go get that locally.

Apparently, this is a good way of getting

files across your systemsthat you’re trying to get into.

So now that’s our bash file,

we can confirm all right,does this happen to other people?

And we can see here, hey,this system just connected to it.

Cool.

So we can just turn offthat little web server.

So we can confirm eleven, 3504, that thisis definitely the exact same file.

So once it’s over here, we can change mod.

No, let’s just go to the questions.

Let’s just go back.

I’m getting ahead of myself.

So we’ve gained access.

We’ve got low privilege uploadbash executable to NFS.

I was supposed to upload to the NFS.

Yeah, we already had a mountconnecting our two machines.

Well, I’ve done it in a slightlydifferent way, so let me just go back.

This is what I get.

So what we could have done is copy our

bash to our temporary mountfolder or directory.

So we’ve copied that and puts it overthere, and then it uploads the files.

It just takes a little bit.

So in this case, if we looked atwhere’s the mount is, it in mount.

If we looked up Lsmn, I don’tknow where the mount is on here.

Shared folder.

Is that where it goes?

Okay, I’m not sure where it goes,but I got it over there.

Anyway.

First change directory to the mount forthe NFC should still be mounted.

And then using the homes directories oh,

wait, it was just in thewasn’t it just in our file?

Yeah, it was the home file.

So it would have just been there.

So I copied it over, I think.

Download CP.

Copy that to download bash.Yes.

So we’ve got it over there.

Now we’re going to add SUID bit permission

to the bash executor we just copied usingplus permission bash.

What letter do we setthe SEO bit using change?

Actually, I’m not sure.

Okay, let’s problem solve this.

So this is our file right herethat we need to change over.

So we need to see an S somewhere here.

I don’t know if it’s like,for the executable, so let’s just try.

So we go ch changemode plus S.

I think two bash and list that out again.

And now we have sick.

That’s right.

I probably should have done that.

Okay, cool.

I probably should have donethat before I done it here anyway.

Let’s do a sanding check.

Let’s just checkthe permissions of the bash.

That’s what I just did in Lslabash.

What is the permission look like?

So I don’t know if it wants all of it.

I’m just going to copy that over,

but it says change permissions or bashis not permitted because we’re not user.

So because I’m doingin the wrong one, right?

Because I need to do itactually through yes.

I need to go change mod plus S.

I need to do it in the right place.

That’s what I’m missing.

That’s what I’m missing, I think.

Cappuccino Bash.

So I can do it here becauseI’ve got privileges.

But if I look over here,if I look over here and it’s added,

but it’s not executable for everyone,can I add change mod plus X?

Can I do this and then do this?

Cool.All right.

This is looking a little bit morelike what I should have got.

Read, write specials, figured it out.

So this is good learning.

So changing the permissions from yourmachine is what’s, misconfigured?

We shouldn’t be ableto do that, obviously.

All right, now SSH into the user,which is where I’m already at.

And this is what was confusing me.

And Run P persists with permissions.

So we can just go bash P and go.

Who am I?

And we’re root.

We did a baby.

Let’s list out what we’ve got.Wait, where am I?

Print working, directory home and capture.

So let’s just change directories

to go to our root folderand then we can list out that.

Then we can cataparroot textand looks like we’ve got our flag.

Honestly, it felt pretty good because sortof things went a bit pear shaped there.

Did things.But you know what?

It’s all part of the learning,so it’s all good.

That was the first partof Network Services, too.

Task is one to four.

Go ahead and we’ll terminate that.

If you enjoyed this, let me know.

Comment, like, all thosesort of good stuff.

If you have any comments for videosor anything, just let me know.

Reach out if you want to.

Yeah, that was fun.

That was really fun.

Stay tuned for part two, which will begoing over SMTP, so that should be fun.

And then, of course, part threewill finish off with my SQL.

So thanks.Stick around.

If you’ve made it this far,

you’re absolutely the legendand I will see you next time.

Cool, thank you.

</div><div class="hs-embed" data-hide_video="true" data-id="72e624b2836b40ad8f26e458c5fb59e7" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>