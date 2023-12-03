---
id: 5717
title: Network Services 2 TryHackMe Part 2 SMTP
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5717
url: "/?p=5717"
---

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/jbwI9Axvpns?feature=oembed" title="Network Services 2 TryHackMe Part 2 SMTP" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:600px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ Network Services 2 TryHackMe Part 2 SMTP](https://www.happyscribe.com/?utm_source=embed-player&utm_term=5fa7cf677db74efeb04d23d87fcd37fc "Network Services 2 TryHackMe Part 2 SMTP")

Welcome back.

We are going to be doing the restof Network services two.

And this is now part two.

We’re going on to SMTP.

So we’re going to be doingtasks five, six and seven.

And then we’ll be finishing off8910 eleven in the next video.

If you want a written write up,the link will be below.

And if you need anythingelse, please reach out.

And if you want to like videosubscribe, do all that stuff.

Awesome.

Okay, with that all out of the way,let’s go to task six and just hit Start

machine so we can get our VM up andrunning and we’ll go over to task five.

Understanding SMTP and wecan just go on here.

What is it?

So it stands for Simple Mail Transfer

protocol is utilized to handlethe sending of emails.

So you probably use this protocolbefore whether you knew it or not.

And in order for this to work,

there are a pair of support emailservices compromising of Pop and IMAP.

Together they allow the user to send

outgoing mail and retrieveincoming mail respectively.

So, SMTP server performsthree basic functions.

So it Verifies who is sendingthe emails through the SMTP server.

It sends the outgoing mail and if

the outgoing mail can’t be delivered,it sends the message back to the sender.

Cool.

So most people will have encountered SNCPwhen configuring a new email address

on some third party emailclients such as Thunderbird.

I’ve had done this like setting upfor friends or family or for work purposes

and as when you configurea new email client.

Cool.So Pop and IMAP.

So Post Office Protocol and thenInternet Message Access Protocol.

So they’re both email protocols who are

responsible for transfer of emailsbetween client and a mail server.

The main difference is Pop’s moresimplistic approach of downloading

the inbox from the mail serverto the client, where IMAP will synchronize

the current inbox with the newmail on the server.

Those two options are sort of like

the implementation of IMAP personallyand downloading anything new.

So this means that changes to the inboxmade on the computer over IMAP will assist

if you synchronize and then synchronizethe inbox from other computer.

Popper imapse is responsiblefor fulfilling this process.

So how does it work?

We have a little diagram here.

Email delivery functions much the sameway as physical email delivery system.

User will supply the email

a letter and service the postal deliveryservice and through a series of steps

we’ll deliver it to the recipient’sinbox or post box.

So the role of the SMTP server in thisservice is to act as the sorting office.

So the email is picked up and sent

to the server, which thendirects it to the recipient.

We can map the journey of an email

from computer looking likethis user to the server.

SMTP server going out, pinging around,

going to the i, map or Pop serverand then going to the recipient.

So it lists out the order.

Going to just skip past this for now.

And there’s a good article here,which another article is on my read list.

What runs SMTP software is readilyavailable on Windows Server platforms,

with many other variantsbeing available on links.

Windows Server,

they’ve got email client Bob server justbuilt into it if you activate it,

more information if you want technicaldevice implementation of it, go like that.

Cool.

All right, let’s go overthe questions together.

And we’ve got what does SMTP stand for?So we had it up here.

We’ve got simple mail transferprotocol so we can pop that in.

What does Smt handle?

The sending of so what does ithelp or what does it actually send?

Emails.Yeah.

39, baby.

What is the first step in the Smt process?That’s what I skipped.

So let’s go back here.

So we’ve got the mail user agent,which is either your email client or

external program, connectsto the server of your name.

So connects or something.

So we wantthe mail user agent connects to the SMTP

service domain,initiates the SMTP handshake.

That’s what we’re looking for.

So it connects, but it authenticates.

This connection works over SMTP port,which is usually 25.

So looking for the SMTP handshakeand what is the default port?

25.That’s the well known port.

Something that’s good to memorize,I definitely have.

Where does SMTP service send the email?

If the recipient service is not available,it can’t be accessed.

Unavailable email gets put into the SMTP

if it can’t reach it.

If the recipient server can’t be accessed

or is not available,the email gets put into an smtpq.

Okay, not exactly back to the sender on.

What server does the emailultimately end up on?

So it’s either pop or IMAP.

So we can use that diagram,

ultimately ends up here and thenconnects or gets sent to the recipient.

But ultimately it’son the server, I guess.

Can a Linux machine run an SMTP server?

Yeah, pretty sure everything can.A Windows?

Well, yeah, it’s sammy builtinto the system once you turn it on.

So yeah.Cool.

Awesome.

All right, we are up to the next one,is going to ping our IP.

So we’re going to go on to task six,enumerating SMTP.

So we’ll probably start with another port

scan against the targetmachine and we’ll see.

So we’ll do what we’ve beendoing and we’ll run Nmap now.

And then we’ll go through.

So I found that this

string or string this set of switchesfor the Nmap command,

running A and running T four speeds upthe process and doing all the ports.

This has been working quite well.

I still am skeptical of the T four

speeding it up, but sofar things going well.

So we’re going to run that.

And as that’s running in the background,I can see 25 already.

So I know that’s defaultfrom the last task.

So that’s cool.That’s the default SMTP.

Okay, so let’s get started.

Before we begin, make sure to deploythe room check and enrolling service.

Poorly configured or vulnerable mail

servers can often provide initialfootholds into our network.

But prior to launching intact,we want to fingerprint the server.

Fingerprint the server to make ourtargeting as precise as possible.

Is that sort of this term, fingerprinting?

Is that sort of just like

a way of when you’ve got you’reenumerating,

you’re getting like a fingerprint,something unique to identify servers.

That’s sort of what that means.

Not sure, but it sounds cool.

We’re going to use the SMTPversion module in Metasploit.

Metasploit is an awesomeframework that can do a lot.

There’s a couple of rooms and try Hack Mejust dedicated to learning this tool.

So it’s good to go over this to keeplearning it because it’s massive.

So there’s a set of modules builtaround enumerating or exploiting SMTP.

So that’s cool.

As its name implies,it will scan a range of IP addresses

and determine the version of anymail servers it encounters.

Cool.

Enumerating users from SMTP.

So the SMTP services has two internalcommands that allow the enumeration

of users vrrfy,confirming the names of valid users,

and X-E-X-P-N which reveals the actualaddress of users aliases, endless email.

That’s kind of cool that we can pull

that out without going on to itor accessing it.

Using the SMTP commands,we can reveal a list of valid users.

Okay, we can do this manuallyover a telnet connection.

However, Metasploit comes into the rescue,writing a handy module appropriately

called SMTP enum for enumerationthat will do the legwork for us.

Using the module is a simple matterof feeding it a host or range of hosts

to scan with a wordlist containingusernames to enumerate.

So we mighthave some usernames given to us or we

might have to use just a randomword list of generic usernames.

We’ll see what instructions give us,

but we’ve definitely got ourhost that we can plug into it.

So your requirements as we’re going to be

using Metasploit for this, it’s importantthat you have Metasploit installed.

It is by default.

So if you need it, you can go Apt install.

I think it’s MSF console or Metasploit.

It might probably tell us,but it’s one of those.

But yeah, we should probably do an Apt

update and upgradeand do that in the background.

Okay, so we’re all good.

We can do Apt order remove,get rid of some old packages.

Cool.Okay.

It’s worth noting that you’re checking

will work for the majorityof SMCP configurations.

However, there are other non metasploittools such as SMCP User enum that work

even better for enumerating OS level useraccounts on solaris bias, and CV service.

Enumeration is performedby inspecting the responses.

All these different sowhat were these again?

These were SMCP services.

So it tries to get responses from these.Okay.

Sort of understanding it.

The technique could be adapted in future

to work against othervulnerable SMCP diamonds.

But this hasn’t been doneat the time of writing.

It’s an alternative that’s worthkeeping in mind preparation.

Okay, cool.

So let’s run a port scanagainst the target machine.

Same as last time.What port is SMTP running on?

So my port scan is still goingand it’s going to go for a while.

So let’s try and see if we canjust answer these as it’s running.

Okay, so it’s definitely on 25,

and that’s based on this firstport that’s the scan has told.

And if your skin isn’t showing anything,make sure you use your VB for talkative.

That’s going to see all this informationabout what our scans actually doing.

Okay, now we know what port we should betargeting, let’s start up metasploit.

What command do we use?

So I’m just going to go and open a new

terminal here and just letthat run in the background.

I’m just going to go over to our system.

So we’ve got our scan happening at themoment, so we’ll just let that run.

So for this we use MSF console.

So we should have MSF console.

And let’s search the module SMTPso we can use Q to enter quietly.

So usually you get a big oldbanner message, which is fine.

You can just run MSF consoleand just open it up.

Just Q can take a little while.

I might need to run MSF console and knit

or Msfdb and it but looks like we’reworking so we can search for Smt.

SMTP underscore version.

So here we’ve got.

Set as ID zero.

So this is like our search results.

And if there were other things thatmatched this, we would get a big list.

012-3456 seven.

So this is just set to zero isthe first one that’s come back.

Cool.So this is probably what we’re after.

So what’s the full module name?

We got it now.Great.

Now select the module in the list.

How do we do this?

It tells us here.

So we can go info zero if we wantto find out more information.

Or we can just go use zero.

So we can just go use zero,but it’s not looking for that.

Don’t know.I’m going to come back to that one.

Have a look through the options.

Does everything seem correct?

What is the option we need to set?

So we definitely need to set.

Okay, we’ll look it up.

So we’ve just used zero.

So that selected our tool.

This is going to be the tool orthe module that we’re using.

And we need to set it up.

We can’t just set up so we can usenot get was it set?

Yeah.

So if we look at set, we can maybe

know the differencebetween certain options.

But if we just type in options,we’ve got Rhosts, R port and threads.

Okay, so all three of thesethings are required.

We can see here the port that we’respecifying is already set to default 25.

Because that’s the defaultof SMTP, I assume.

So cool.

But then the rhost.

So this is the actual host or the IP orthe machine that we’re wanting to target.

So we can go set Rhosts to and justpaste in our IP address like that.

That confirms with ourhost is equal to that.

So if you just want to confirm that,you can type in your options again.

And now we can see that.Indeed.

We’ve got it there.Awesome.

So the last step of our thing,we can just hit run, but.

Let’S.Just finish this off.

So we got our host.

I honestly do not know what that is.

Set the correct value of your targetmachine, then run the exploit.

What’s the system mail name?

So we can just run run orwe can just run exploit.

These all sort of just work that willtarget the system with this payload.

Okay, so we’ve got SMTP polo, SMTP home.

So it looks like that’s the systemmail name that we’re looking for.

So what was our hand?Looks roughly like an email address.

Sort of what mail transferagent MCA is running.

So if we have a look, this could post fix.

Might be our mail agent.That’s our mail agent.

If you need to send a letter, you post it.

So that was the hint where you post fix.

That’s the mail transfer agent MCA.

Not exactly sure what that is.

I don’t remember that showing up.

I may have skipped over.

That another one.

To lock that in.

Okay, good.

Now you’ve got a good amount

of information on the targetto move on to the next stage.

Let’s search for the SMTP enumso we don’t have to exit or go back.

We can just use searchhere and we can find it.

So again, we can just go use zero because

on the list it’s the first oneand computers start at zero.

So we’re going to go use zero.

And we can see here ourprompt has actually changed.

So we no longer selected this.

We’ve now selected SMTP.

So that’s just asking,what’s the full name?

This is good.

This is making sure that we’re actuallyusing the right tool like this.

We’re going to be usingthe top usernames shortlist.

No.Is my scan still going yet?

I actually don’t know what this is.

Let me just open up.

I’m going to have to download it.

I don’t have it.

I’ve seen a couple of people use this

locate commands to try and find any filelike that, but I don’t have it by default.

So we’ll have to download it.

So it’s amazing collection of Wordlist.

If you’re running Carly Parrot,install Seclists.

Okay.

It’s a part of Seclist,so we can just go apt install seclists

and that’ll grab that for usand then we should have it.

Cool.

I am going to try that locate tool againonce this downloads,

just to see what options do weneed to set in the Word lists.

So if we go options again,we’ve got our host.

So we need to set ourhost and then use a file.

So this is going to be our Wordlist.

So we can see here by default.

We’ve got Unix usernamesset, so that’s cool.

If we just ran this, we may have a chance.

So I’m just going to look up thisand see if I can okay, so this is it.

This is the raw list.

So not that big of a list at all.

I’m fairly confident if I just use thatother default list that it would work.

What I’m going to do is I’m just going toget this right here.

I’ve got to go back here and we’regoing to set the user file to this.

And now I know the file there and I’mgoing to run it and hopefully see

something different because weactually have fed a wordlist into it.

So since it’s not that long,it shouldn’t take that long.

So it’s under usernames.

Was there a usernames?

Man, I’m so blind.

I didn’t even see that.

Okay, can we just list outwhat’s in the usernames?

And there it is.

Okay, I swear I do this.

I just find the longest way to do things.

Anyway.

We have got it working.

Even if I do things the wrong way,I’m going to pause the video.

No, I’m not.Here we are.

I will pause the video to figureout what the hell that question is.

But we have foundadministrator has worked.

So that’s cool.And my skin finished.

I’m just going to cap thisout and grab three open.

So still only two ports open.

Good that we did the whole scan justin case there was something else.

So what was it?

Administrator?

I’m so dumb.

I just wasn’t understanding the question.

Thank you for the write up.

Now select the moduleand list the options.

How do we do this?

That was on me for not understanding it,but it did trip me out.

Now select the module is like one part.List the options.

How do we list the options?

Would have just made my brainunderstand that a little bit better.

I was like, how do I select it,and what’s the option?

How do I just select it first?

Okay, I was doing it,but I didn’t understand anyway.

Cool.

So let’s go on to task seven,exploiting SMTP.

So let’s go over what do we know?

Okay, at the end of the enumeration

section, we have a few vitalpieces of information.

We have a user account,so that was through our top list.

So we have administrator.

Administrator and a type of SMTPserver and operating system running.

So yeah, we know this.

It’s running on Ubuntu.

We have the name.

Okay, so we know from our port scan

that there’s an open porton this machine is an SSH.

So that’s also true.

We have an SSH here.

We’re going to use this information to try

and brute force the password of the SSHlogin to our user preparation.

So it’s advisablethat you exit metasploit.

Right nowI’m just going to copy paste this

information, but I knowit’s probably a better way.

So I’m just going to copy pastethis and just chuck it over into a file.

And what did we actually find?

You know, I’m just goingto call SMTP underscore enum.

I was going to paste itin there just for our records.

So we got a scan.We’ve got everything from there.

Cool.So we can just exit out of everything.

And I don’t think we need checklists over.

Okay, so now we’re goingto go over to Hydra.

I believe Hydra is installed,and I have used it.

Cool.

So we’re going to be usingso here’s our command, hydrate.

So this is going to specify the speed.

I’m going to play aroundwith that maybe login got username.

So we can go down here.

Points to the account,points to the file of possible passwords.

So in the past, we use Rockyu.

So we’re going to be using Rocky againbecause we’re doing passwords VV for both.

And then we’re going to be tryingto exploit the SSH on our machine.

Cool.So this is pretty simple.

So we can just follow the bouncing ball.

So T for I think it’s threads or amountof tasks is 16,

but I think by default, it’s runningat four, but we can go up to 64.

So, yeah, I’m just goingto try 64 to see what happens.

Administrator and then we’ve got P for thepassword list that we’re going to try.

So go user, they go sharewhen you go wordlist.

Then when you go to the Rocky text file,

v, uppercase v, specifyour IP and then SSH.

So that’s looking pretty good

as long as I spelled things rightand the 64 doesn’t throw us any errors.

Let’s try and runthat and see what we get.

So revolving both error, error, error.

See some more attempts.

It’s working pretty fast and wehave a success highlighted here.

I should have teared this out.

I forgot to tear it outfor record keeping.

So what is the passwordat the enumeration stage?

So we’ve got a password here.Great.

Now let’s log into the SSH.

So we can go SSH

and we can go into adminstrator accountat our IP address and we can hit enter.

That’s going to say,hey, sure, fingerprint.

What’s the password?

Copy that, paste it in thereand hopefully we’re in.

Cool.So let’s list out what we’ve got.

We have a dead letter.

I’m curious, is that what somethingtried to send or something?

Okay, we have a mail.

So I guess this is justa part of the SMTP.

Then we have an SMTP fileand that is our flag.

Cool.

Copy that, paste that in,and that is part two complete.

Well done.

If you’re following along at home,congratulations, you’ve made it this far.

We’ve only got one more part of three or

four tasks left of this room,so that should be up soon.

If you’ve enjoyed this video,thank you very much for following along.

If you got this far, congratulations.It’s very cool.

I hope you’ve learned something and I hope

that you’re going well on yourcybersecurity journey.

I will see you in the next one.

Thanks for staying around.

</div><div class="hs-embed" data-hide_video="true" data-id="5fa7cf677db74efeb04d23d87fcd37fc" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>