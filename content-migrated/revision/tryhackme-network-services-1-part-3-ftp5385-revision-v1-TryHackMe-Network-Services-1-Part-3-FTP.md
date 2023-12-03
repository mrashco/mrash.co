---
id: 5724
title: TryHackMe Network Services 1 Part 3 FTP
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5724
url: "/?p=5724"
---

Let’s go, TryHackMe Network Services Walkthrough Part 3, welcome! Step 1 learn, step 2 enumerate, and step 3 exploit… but what? Well, a variety of network services and misconfigurations of course, this time it’s FTP. Watch the Network Services Walkthrough for TryHackMe’s room, Part 3 FTP.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/lpjifLzyX8Q?feature=oembed" title="TryHackMe Network Services 1 Part 3 FTP" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ TryHackMe Network Services 1 Part 3 FTP](https://www.happyscribe.com/?utm_source=embed-player&utm_term=c9f0b31784d84e14b0f77b48ea9339ff "TryHackMe Network Services 1 Part 3 FTP")

Welcome back.

We are going through Network Services room

in Triacme, and we’re up to task eight,understanding STP.

And we’re going to go through our lastthree or four tasks here together.

So, on task nine,let’s just start up our machine.

That’ll take a minute.

So by the time we get through this,we’ll be there.

And just a heads up,a blog post will be linked below so you

can have a written write up of this ifyou need to go to anywhere specific.

Plus, there will be the timestamps below,so you can skip ahead in the video.

So written or video, whatever you prefer.

Here to help.

All right, let’s go over what is FTP?

So it stands for File Transfer Protocol,and as the name suggests,

protocol to use to allow remotetransfer of files over a network.

It uses a client server model to do thisand as well as will come on to later,

relies on commands and datain a very efficient way.

So how does it work?

A typical FTP session operates using twochannels, a command,

sometimes called a control channel,and then a data channel.

So as the name implies,the command channel is used

for transmitting commands as well asthe replies to those commands,

while the data channel isused for transferring data.

Command, data channel.

Cool.

So FTP operates usinga client server protocol.

This client initiatesa connection with the server.

The server then validates whatever login

credentials are providedand then opens the session.

While the session is open, the clientmay execute FTP commands on the server.

So then there’s active versus passive.

Active is FTP.

The client opens a port and listens.

The server is requiredto actively connect to it.

And a passive server opens a port

and listens passively,and the client connects to it.

So I don’t really understand FTP.

These concepts don’tmake full sense to me.

I understand transferring files over this

protocol, but yeah, I need to definitelydo a bit more research into this.

But anyway, I got the sort of gist of it.

Sofor more detail, we can go and read that,

which I have linked offfor a later reading.

So I really need to do that.

So what communication model does FTP use?

So we do have the client server model, soI’m going to say we’ve got client server.

Cool.And what’s the standard FTP port?

So it didn’t actually sayit in the information.

We can do a quick search off memory.

I think it’s either 20 or 21.

I’m going to go 21.

Cool.

Because I know that there is secure FTPand it’s not 22 because that’s for SSH.

So not really sure how many modesof FTP connections are there.

So if we look at our

active and passive, I think is whatwe determine in connection modes.

So we’ll go for two.Cool.

So that is our task eight.

So moving on to task nine.

We should have our IP by now.

Let’s just make sure that we cansee our machine via a ping request.

Sometimes you don’t see it not a bad thingjust depending on the room,

but in this case, that is justwhat we need to do to see it.

Okay, so let’s get started.

Before we begin, make sureto play the room and enumerate.

So we’re going to use Nmap and we’regoing to try and find out what we can.

So as I read this, let’s justgo ahead and run our Nmap.

Did you just see that weird thing,having the multitannels?

I don’t know.

So when I go VV for verbose,I hit enter, hit up.

So let’s just try this again for both.

We could do a I think I wantto do T four to speed it up.

NowI don’t know if we need to do all

the ports on this and it’s not a bad idea,so might as well.

So let’s just output this to a normalformat and we’ll just call it scan port.

And we’re going to do it against this IP.

And just as a backup, I’m just going totease out to Scanport Bak, just a backup.

Now I think this is going to give useverything going to let that run.

So using the A is going to tryand use the NSE Nmap script engine.

I’m going to try and find otherscripts to run against it.

So that’s what we’regoing to get from Dasha.

I don’t know if it’s a good idearunning this on the initial scan.

I don’t know if this I’ve been not doingthis because I’m just like I just want

to find what ports are open and thenwe can go further from there.

So anyway, you let that run and let’sjust keep reading while that’s running.

So the method,we’re going to be exploiting an anonymous

FTP login to see what files we can accessand if they contain any information

that might allow us to popa shell on the system.

This is common pathway in CTF challenges

and mimics a real life carelessimplementation of an FTP server.

So we’re going to be logginginto the FTP server.

We’ll need to make sure we’re using an FTPclient which is installed on our system.

There should be one installed by default

on Linux operating systemssuch as Cali Parrots.

I’m using cali in VirtualBox.

You can test if there’sone by just typing FTP.

So let’s just go over,

see if we make sure we’ve gotsomething cool into the console.

If you brought up, we have a prompt,so alternative enumeration methods.

So it’s worth noting an extra space here.

It’s worth noting that some vulnerableversions of in Ftpd and some other FTP

server variants returndifferent responses to the CWD.

I have no idea what this means.

Command for home directories which X

exists and those that don’t it can beexploited because you can use issue.

Okay, there’s a vulnerability.

It’s a little bit above my paygrade at the given moment.

We’ll come back to that at another time.

So we’ve got the linksthat I opened up before.

I got to be honest, I don’t go to thesesites that often, so must do that.

Okay, so run an Nmap scan of choice.

So in my case, I’ve run this.

So you can follow alongor you can do your own.

How many ports are openon the target machine?

So as of right now, I can only see one,

so I’m just going to go ahead and seeif it’s going to be the only one.

So, no, there’s more scans to do,there’s more ports to find.

So we’ve got about ten minutes.

Usually I find these scans run for upto 20 minutes and I don’t know if that’s

based on my connectionor the box connection.

So, yeah, not sure.

So we do have a 21 here,so if I type in 21 for the port,

I don’t know if it’s FTP,but I’m assuming because that’s

the default and they haven’tchanged it like the telnet one.

So what variant of FTP is running on it?

So we’re not going to get that information

until this finishes,which says it’s about ten minutes.

So I’m going to pause it there and we’llcontinue once this scan is finished.

So we’ve got our scan that’s completed,

so it took a little bit,but that’s all right.

Let’s try to get the OS runningto try to run a couple of scans.

So let’s go down to here.

So we’ve got a lot that were closed,but we’ve got our TCP running on 21,

which we know is FTP,and it used a script called FTP Anon,

trying to see if we can login with anonymous, and it did say already

that we’re going to try and do that,so there is just further communication.

So do we have anything else that is open?

So how many ports are open?

So if we look here,I can only see one port that’s open.

I think I already tried this.

Was there anything else that I’m missing?

6500 are closed.

So is it technically nothing is open,

or is there something elsethat I’m just not seeing?

I’m notfor three, but that doesn’t say

that there’s something else openthat’s just using trace route.

So kind of confused,I didn’t see anything else.

Now I did use the T four,which speeds up the process.

So this is an instance where Ithink that has actually missed.

So I’m going to do something,I can just guess.

So there’s another port herethat’s actually been missed.

So what I’m going to do is I’m going torun this again, I’m going to continue on.

I’m just going to let thisrun in the background.

I’m just going to put this as two.

I’m just going to do this without the T

four, just to see if it picksup on those other scans.

So I’m going to let that runand we come over here when you continue.

So let’s just change Directories intoour documents, our trihack me,

our network services, and we can seeour scan too, which is in process.

But we can just scan out I mean,

cut out that scan and we cansee what variant of STP.

So we do have this version.

So I’m assuming that that’s the variantwhich was what we were talking about.

I think that must be a different variant.Not sure.

Don’t quote.

Me, but I’m going to assume that thisis the variant that we’re looking at.

Great.

Now we know what type of FTPserver we’re dealing with.

We can check to see if we are able to log

in anonymously, which if we use that Aand used that FTP, it’s confirmed.

Yes, we can.

What is the name of the filein the anonymous FTP directory?

So we can just log in basically.

So let’s run FTP and then justagainst this IP.

Is that all?

Cool.

So going into so let’s just try

anonymous and just nopassword login successful.

So there is an unsecure or insecure.

Is it unsecured or insecure?

I’ve seen it written both ways.Cool.

So what is the name?So can we just list out what’s here?

So we have a publicnoticetxtr in this current directory,

so we can read it and wecan’t actually write to it.

So can we cat out this public TXT file?

Invalid command.

So what do you think?

Username?

So we just need to look uplet’s just look up help.

See, we’ve got a list of things.

I’m shocking with these and Idon’t know if it was Get or show.

Let’s have a quick look through.

Was it more let’s try

I think Fget or Mget?

I think that was to download the file.

I think that’s what it is.

I don’t know if there wasjust like a tatted out.

So if I could just m get that,would that m get this?

Yes.

And if we just changeback to where we were, network services.

Did that download that file for us?

There it is.Just over here.

Public notice.So Mget did get it hooray.

So we can cut it out on our local system.

Message from system administrators.Hello.

I hope everyone is aware that the FTP

server will not beavailable over the weekend.

We will be carrying outthis is sort of behind me.

Let’s bring this over here.

Carrying out routine system maintenance.

Backup will be made to my account.

So I will I recommendencrypting any sensitive data.

She is Mike.

So what do we reckon ourpossible username could be?

We’re probably going to gowith Mike on that one.

So check back over there.Great.

Now we have some details about FTP serverwe can crucially a possible username.

Let’s see what we can do with that.

All right, so up to task.

Ten exploiting FTP.

Wow.

Types of FTP similar to telnet.

When using FTP, both the commandand data channels are unencrypted.

I guess that’s why secure FTP exists now.

Any data sent over these channels can be

intercepted and read with datafrom FTP being sent in plain text.

If a man in the middle attack took place,

an attacker could reveal anything sentthrough the protocols, such as passwords.

We have an article herethat explains art poisoning.

Very, very cool.Cool.

So the method breakdown from ournumeration stage which we’ve done.

There is an FTP server running on this

machine, which we know about, wherewe have a possible username of Mike.

And using this information, let’s try andbrute force using a tool called Hydro.

So it’s a very fast online passwordcracking tool

which we can perform a rapid directoryattack against more than 50 protocols.

So remote desktop, secure cell shocket,

secure, shell, SSH, FTP, http, https, SMB,and several databases are much more cool.

So I’ve only used Hydralike a couple of times.

I’m not that familiar with it, but yeah,we can go through and definitely use this.

So let’s back on out of ourFTP anonymous install.

Goodbye.

Okay, just out of interest,we’ve still got this running

in the background and it saysit’s going to take an hour.

I guess that’s why we like to use the T

four to speed it up becausethat’s kind of ridiculous.

I’m probably just going to give up onthat and we’re just going to continue on.

But if you’re interested in how that goes,

let me know and I can putit in the written right up.

Okay, so we’re going to use Hydra.

So here’s a breakdown of ourcommand that we need to do.

So t four number of parallelconnections per target.

I don’t know if that stands for threading,

I don’t understand it, but I thinkthat’s like threading or just target.

So using four per however many tries can

do it once L for the login or usernameuppercase P for the wordlist.

In this case when you use the infamous

Rocky VV, which I think is verbose,sets to very verbose, and then the IP.

And then we go to the protocolwhich will be FTP.

Cool.

So if you didn’t know in your user shareyour Word lists,

if you look in here, you actually havesome this is built into

Kali or Kali Linux, however you wantto say it, that’s where Rockyu is.

And it might be zip.

I think you use Gzip,so I think it was D for decompress.

So if yours is compressed, just like Ijust did, hit list, the list out there.

And if it’s compressed,

you just need to uncompress itand then you’ve got it there.

I’m not sure why it comes that wayin Linux or Kali, but yeah, it does.

So let’s go ahead and run Hydra and just

see if there’s anything elsethat we can pass through.

So we can pass through files orcapital T’s for different tasks.

So we got time.

So there’s a lot that we can do here.

Service.So just off memory,

this was what I remember puttingthe service first FTP and then the IP.

I thought that was the format.

I’m just going to try this and if it’s

wrong, I’ll just go backto what they recommend.

So I don’t know if this is like because

it’s an older version of Hydra orthere’s just different ways to enter it.

I don’t know, but okay,let’s give it a go.

So, Hydra,

I’m not going to specify the T just outof interest because I was mucking around

with another one and Icould do it up to like 64.

So I don’t know if that creates issues.

Like if the faster it goes,

it’s like you can get incorrectinformation, sort of like Nmap can do.

So I don’t know, I’m just goingto leave that out just for now.

So we do have the possibleusername of mike.

So we type mike in, we’ll gouppercase P for that wordlist.

So let’s use an absolute file path

to the wordshare wordlist,

and then we’ll use the RockYou,and then we’ll use the double verbose.

I don’t know if we needto do capital V for that.

I’ll just do it and then I’m goingto go FTP and then the IP address.

So if this spits out an error,I’ll go back and see what they say.

But yeah, wow.

So it’s working and we havegot a successful login.

So the verbose was really cool becauseyou could see exactly what it’s trying.

So if you don’t know that the Rockypassword list, these are all the most

common passwords that were in the Rockydatabase, is all story to it.

But yeah, it found mike and password,

so probably could have justguessed that, but good to know.

I should have also actually ranthis and teared it into a file.

Like I could have just called hydracould have done that.

So then I’ve got a backup of it, butbingo, now we can log in with that user.

So remember we logged inwith the yes, that’s the right one.

So log in through there.

So the name we’re going to log in is mike.

The password is going to be password

and then we should be in FTP,so we can go list hooray.

And there’s FTP and FTP text.So it says.

What is FTP?

So let’s use that Mget to transferthat over to our

download that list that out and we’ve got

are you sure you want to do that?

Yes, please.

And there we go.

FTP So what I’ll do is I’ll just exitand I’ll just put it on the big screen,

cat out FTP text,and there is our final flag.

We did it.

So that’s really fun.

I really enjoyed this room.

Even going through this another time,

there’s still lots that Ihaven’t fully grasped.

So this is really good for me to gothrough and I hope it was good for you.

So you got one last task therein eleven and we can just hit that.

So, yeah, if you enjoyed this, awesome.

Thanks for coming along with me.

If you want, stick around,

there’s going to be more videos,some more tri Hackney Content coming up.

If you need anything,just reach out, leave a comment.

Let me know if you get stuck on anything

or you just want to talkabout the room or anything.

Happy to do that.

Like I said, at the start of the video,there will be a written write up.

So if you want the written write upto go through, that will be below.

Feel free to subscribe to thenewsletter if you would like to.

Otherwise yeah, I’ll seeyou in the next one.

Bye.

</div><div class="hs-embed" data-hide_video="true" data-id="c9f0b31784d84e14b0f77b48ea9339ff" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Task 8 Understanding FTP

Questions:

- What communications model does FTP use? client-server
- What’s the standard FTP port? 21
- How many modes of FTP connection are there? 2

## Task 9 Enumerating FTP

Questions:

- How many ports are open on the target machine? 2
- What port is ftp running on? 21
- What variant of FTP is running on it? vsftpd
- What is the name of the file in the anonymous FTP directory? PUBLIC\_NOTICE.txt
- What do we think a possible username could be? mike

## Task 10 Exploiting FTP

Questions:

- What is the password for the user “mike”? password
- What is ftp.txt? THM{y0u\_\*\*\*\*\*\*\*\*\*\*\*\*\*\*}