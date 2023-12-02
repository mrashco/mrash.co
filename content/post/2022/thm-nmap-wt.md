---
title: TryHackMe Nmap Walkthrough
author: Mr Ash
type: "post"
published: 2022-03-19
lastUpdated: 2022-11-05
url: "/tryhackme-nmap-walkthrough/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/X6uEAEkx/1eadb440-2474-4e54-aa4b-8d44ba446101.jpeg?v=66cc324e4f0c17fcae9c0502df29cfe4
categories: Cyber
tags:
    - nmap
    - Networking
    - TryHackMe
---

Welcome to another [TryHackeMe](https://tryhackme.com/) Walkthrough, this time the [Nmap room](https://tryhackme.com/room/furthernmap) from [TryHackMe’s Beginner Learning Path](https://tryhackme.com/path/outline/beginner). In this TryHackMe Nmap Walkthrough, we’ll go over all 15 tasks and you’ll see every detail you need to not only complete the Nmap room but understand it too.

For a quicker look at the Nmap Room, see [TryHackMe Nmap Room Notes](https://mrash.co/tryhackme-nmap-room-notes/), enjoy the TryHackMe Nmap Walkthrough, happy hacking.

*Disclaimer, see the [video version](https://youtu.be/I3mynoAsgJI) or the previous Linux Fundamentals [Part 1](https://mrash.co/linux-fundamentals-1-tryhackme-walkthrough/), [Part 2](https://mrash.co/linux-fundamentals-2-tryhackme-walkthrough/), or [Part 3](https://mrash.co/linux-fundamentals-3-tryhackme-walkthrough/) if needed. For help getting started, see [Linux Quick Start Guide](https://mrash.co/linux-quick-start-guide/) and [Starting Out In Cyber Security](https://mrash.co/starting-out-in-cyber-security/).*

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/I3mynoAsgJI?feature=oembed" title="TryHackMe Nmap Walkthrough" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">[ TryHackMe Network Services 1 Part 2 Telnet](https://www.happyscribe.com/?utm_source=embed-player&utm_term=e41dd55eff51408a9d95b18f998801c9 "TryHackMe Network Services 1 Part 2 Telnet was transcribed")

Hello, welcome back.

We are going to be doing some morenetwork services on try hack me.

So there’s going to be a walkthrough.

We’re up to task five,understanding telnet.

And I just need to tell you that there isa written right up below if you look

in the description and timestampsare going to be in the video.

So if you just wantto jump along, go for it.

Okay, with that out of the way, let’s gothrough task five, understanding telnet.

If you haven’t already,

start your virtual machinethat we’re going to be looking into.

And as always, I’m sort of justgoing to go over the info roughly.

I’m not going to go into everything,but what is telnet?

Telnet is an application protocol

which allows you to usewith the use of telnet client.

Wow, great start.

To connect to and execute commands

on a remote machine that ishosting a telnet server.

So application protocol,so replacement, it’s been getting replaced

by SSH because everything’sin clear text or plain text.

So you’re not going to see telenet,which is kind of funny because I did

actually see it in my routeror my old router.

Good thing I don’t have that anymore.

How does telnet work?

So the user connects to the server

by using the telnet protocol, which meansentering telnet into a command prompt.

The user then execute commands

on the server by specific telnetcommands in the telnet prompt.

So we need to go from our shellinto telnet terminal or prompt shell.

You can’t connect to a telnetserver with the following syntax.

Cool.Okay, so what is telnet?

So telnet is an application protocol.

What has slowly replaced telenet?

So that is SSH.

So you’ve probably done a bit of SSH

already connecting to the virtualmachines, intra hacking.

How do you connect to a telnet serverwith the IP of three on the port 23.

So we store here telnet,that should be as easy as going, hey,

we want to connect to telnet, we wantto use this and we want to go to port 23.

And the lack of what means that alltelnet communication is in plain text.

So it did allude to up here that it’sall in just clear text or plain text.

So if we look at our hint, what does

the modern intent use useto communicate securely?

So we can think about SSL and Https.

All of these formsof communications encrypt our data.

So there’s just no encryption on telenet.

So any protocol that usesplain text or is not cool.

So yeah, encryption, we want encryption.

We want our data to be alljangled up and confused.

So if anybody sees it,they can’t understand it.

Cool.

So task six enumerating telnet.

So let’s get started before we begin,make sure to deploy the room.

So I’ve done that.

So I’ve got my IP up here.

Yours is going to bea little bit different.

We’ve already seen how key enumeration canbe how key enumeration can be

in exploiting a misconfigurednetwork service.

However, vulnerabilities that could be

potentially trivial to exploitdon’t always jump out at us, man.

This is something that keeps coming up

for me because when we run, like, scansand stuff, it’s just like a wall of text.

I find it really hard to siphon through.

I don’t know if it’s the same for you,but yeah, this really resonates with me.

So for that reason,especially when it comes to numerating

network services, we need to be thoroughin our method, which I’m learning.

Port scan.Let’s start out the same way as we usually

do a port scan,to find out as much information as we can

about the services application structureand OS for the target machine.

Nmap going to use Nmap.

So first question here is how manyports are open on the target machine?

Okay, so we’re just going to runan MMAP scan against our target.

But we do want to adda couple of switches here.

So some of the switches that I’m learning

is like double BV for both sowe can see the information.

The other one that I forgetis outputting it into a file.

So we can output into scan ports.

We can just output that into a file.

But I’ve also learned if we Tea this outso this is a pipe command at the end.

So we’re going to pipe the output of this

through another command called T, which isgoing to put it into another file.

And I’m just going to makethis a backup file.

The reason for this is I have learned

from my short time doing this is this isgreat to get your final results

of the scan using the O Noutput to a normal file.

But just in case I cancel the scan or

something, this won’t actuallyrun until it’s finished.

So if we just tee out the results,you’re going to get everything.

So it’s good.

Just have a backup fileor just not do this part and only do T?

Whatever.

I really like using PN for ping,but I don’t know if that’s going to work.

Also,we don’t want to set aside ports just yet,

but I’m going to speedit up using T three.

So T one to five is how fast it can go.

So I’m just going to use T three.

I think that’s fine.

Let’s just see what we get.

Okay, so our port scan hasfinished and we’ve got an 80 one.

That’s the only thing openout of all 65,535 ports.

Just this one.

And this is what theycall a nonstandard port.

So let’s go over these.How many ports?

So we just got the one.

What port is this?

So it’s on TCP, it’s openand we’ve got TTL.

So we know that it’s Tal net,but it’s actually asking us for the exact

number, which I thoughtit wasn’t for a second.

This port is undecided but stilllists the protocol it’s using.

So what protocol is this?

So it’s on TCP.

So transmission, communication.

Communication protocol.

Yeah, I think those weresimple stands for now.

Let’s rerun it.So we’ve already done it with p to get

everything so we don’tneed to run anything.

It says how many ports show up as open.Nothing.

There’s nothing else.Everything else is closed by this one.

So that’s why we want to run that.

And that’s good.

So don’t be like me and get trippedout when we don’t see anything.

Yeah.

Based on the title returned to us, whatdo we think this port could be used for?

Something.A something.

So this is some sort of communication.

We know it’s going to be telnetbut like a service.

Are we looking for a service?

Based on the title return to us, what dowe think this port could be used for?

Communication.

Who could be long to gathering possibleusernames as is an important step.

Sorry.Did I miss something?

It’s important to try everynew range you gather here.

The exploitation stage.

Based on the title return to us.

So what have we got from this so far?

We’re not running anythingelse at this point.

I know what I need to do.

I know what I need to do.

So I need to actuallyspecify against port.

So we’re going to actually just go

what happens 80 two?

Because that’s the port we’re goingto do another 18012 this time.

We’re just goingto aggressively look at port.

80120n earth is just happening right now.

What’s the actual watt?

Okay, don’t know whatthat was but we’re good.

We’re good.We’re good.

I’m going to calm down the speed.

So let’s just run this against isone port to get more information.

That’s what was tripping me.

I haven’t further enumerated using nmap I

wasn’t supposed to useanother actual program.

Supposed to be properly enumeratedhow good I am at this.

Anyway.

I will understand cybersecurityand penetration testing.

So we’re going to let this ride run.

The last one took a while.

So unmarked.

Go ahead and pause againfor this to finish.

All right,

so we have got our scan completed,this time using the dasha for aggressive

and all trying have used the NSE orNmap Cert scan engine, script engine.

And we found something under here.

So this is what I was missingearlier, a back door.

So there’s something placedhere to connect back to.

So in this case, the usernamewe can assume might be Skitty.

Always keep a note of information you find

during your installation so you canrefer back to further exploits.

Absolutely.

So if we list out everything, so I’ve got

the whole scan portand then I’ve got the 812.

So if I ever need to, we can goand use 812 and get this scan back.

So always have the backup or just files.Awesome.

Okay, so let’s go over to exploiting now.

So, types of telenet exploit.

Types of telnet exploit.

Telnet being a protocol is in itself

insecure for the reasonswe talked about earlier.

Plain text, no encryption.

So it sends everything pretty much.

And there are CVE,can’t remember the CVE,

but basically known vulnerabilitiesfor telnet clients and service systems.

So we can look up here and here.Cool.

So common vulnerabilities and exposures.

Got to try and remember that one.

Common vulnerabilities and exposures.

It’s a list of publicly disclosedcomputer security flaws.

So when someone refers to a CVE,

they usually mean the CVE ID numberassigned to that security floor.

Known vulnerabilities.

Okay, so method breakdown.

So from our new numeration stage,

we know there is a poorly hidden telnetservice running on this machine.

The service itself is marked asa backdoor we possibly use, named Skitty.

So connecting to telenet,

we can use the telnet that we hadspecified on the port that we know.

So from the earlier

it was 23 as an example,but in this case, we’re using 80, 112.

So that’s the port that we’re usingto connect over to this machine.

And we’re going to be using the IP.

So we have got a connection, skis backdoor type help to see what we can do.

We can go run command,but I don’t know any commands.

So this is at least where we cando some sort of reverse shell.

So reverse shell’sconcept of getting the machine to send

back a shell to our machinethat will be listening.

So we can see here, victim connectsto an attacker on a listening port.

So we can try and executesome sort of reverse shell.

Honestly, I’m still gettingmy head around reverse shells.

And the other type of shell that’s common,which I can’t remember the name of.

All right, let’s try and connectto the telnet port, which we just did.

So great, it’s open.Telnet communication.

What message do we receive?

So we’ve got Skitty’s backdoor type help.

I think it just wants that.

Cool, let’s try and execute some commands.

Do we get a return on any inputwe enter into the telnet session.

I mean, I do get a return from help,

but if I try and run anything,I do get something from help.

But if I try and runanything, no, I don’t.

So the answer is no.

Obviously.That’s strange.

Let’s check to see if what we’re typingis being executed as a system command.

So let’s start a TCP listeneron the local machine.

I’m going to go control shiftR to get a terminal up here.

I don’t know why this trips out.

The fonts really annoying.

So we want to go T-C-P-D-U-M-P-I-P pro

toontontunnel.

So this is going to be listeningto anything that comes over.

This is like the only timeI’ve actually used TCP dump.

So let’s try and go help again.

Do we see anything run?

No, that’s not going to do anything

because we want to see a specificlistening for ICMP traffic.

Right.So now we can use the command ping local.

So if we go run ping

and I’m not going to remember theconfig, just get our local IP here.

Cool.

So we saw that ping request.

So we do need to interact.

So we can actually exit things.

I just need to know the commands to run.

So now use the commands.

Okay, I’m understanding.

Yes, we can see something.Great.

This means that we’re able to execute

system commands and that we’re ableto reach out to a local machine.

So we’re going to generate a reverseshell payload using SF venom.

This will generate encodenetcat reverse shell for us.

Here’s our syntax.Cool.

So we need to do thison our local machine.

So I’m just going to go over a new shell.

So if we run this command

but we’re going to edit it just toput our local IP in here,

which I have forgotten againand I will never remember.

I see how people do likevariables and they put their IP and I

think I should reallylearn how to do that.

This is a part of the metasploit frameworkand they made it a standalone pool tool.

And we’re using the P for payload.

And then this is a builtin payload that we can use.

So I’m just learning MSF.Venom.

So we set our listener host to this,which is us.

So we’re going to try and

tell the machine, hey,connect back to us on this port.

Four, four, four.

So we then have our payload,which is this.

So this is going to tell the machine usingthis command to set up netcat and to

send this connection back to us,which is kind of crazy.

So we can go run paste that in there.

And I’m not going to hit enter.

Because if we hit enter and we’re not

listening, then we’re notgoing to actually hear it.

So we just want to set up Lon netcat so NC for netcat L forbos.

And I think that’s something aboutDNS don’t Rename can’t remember.

And then P.

So we don’t want to do 123-7144 four

because we set it to talkback over that port.

We could set any port.

It doesn’t matter the actualnumber that we set.

So if I go back here and we hit enter

and we go back here,we now have a connection.

So before it was just listening and it

said connect to from unknown,and we have some sort of non interactive

shell, meaning we don’thave the nice prompts.

But if we go like, who am I?

Because confidently we know that it is

running some sort of Ubuntu,Unix or Linux system.

So we can run.

Who am I?

Print working directory.

So we’re in root and we can list outwhat’s here and we can cut out our flag.

Wow, sick.

So let’s just go back here becauseI did go ahead a little bit.

What does the generatedpayload start with?

Started with this.

I don’t know what that command does.

What would the command look liketo set up our listening port?

So netcatlvp I did the end,but it doesn’t matter.

And then listening port.

Yeah, great.

Now we run that and do everything that I

did, and we get this and we cancheck that in there and we’re done.

Sick.That was awesome.

So that was our three tasksfor telnet in our network services.

I hope you enjoyed,I hope you learned something.

I had a couple of troubles here and therewith my end map scan, and that’s fine.

It’s part of learning.

So we can go aheadand turn off that machine.

So if you want to stick around,

I’m going to go ahead and getinto the FTP see in the next video.

So if you want to do that,that sounds cool.

If not, all good.

Let me know what you enjoyed about

the video if you want to,otherwise I will see you in the next one.

Cool, bye.

</div><div class="hs-embed" data-hide_video="true" data-id="e41dd55eff51408a9d95b18f998801c9" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Task 2 Introduction

Nmap is a powerful tool to enumerate computer systems, meaning, it can find out information about a target. But as you’ll learn from this room, Nmap can do even more!

<div class="elementor elementor-5269" data-elementor-id="5269" data-elementor-type="section"><div class="elementor-section-wrap"> <section class="elementor-section elementor-top-section elementor-element elementor-element-650fe30 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="650fe30" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-19d1b1d" data-element_type="column" data-id="19d1b1d"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-widget-wrap"> <section class="elementor-section elementor-inner-section elementor-element elementor-element-75001c1 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-element_type="section" data-id="75001c1" data-particle-mobile-disabled="false" data-particle_enable="false" data-settings="{"ekit_has_onepagescroll_dot":"yes"}"><div class="elementor-container elementor-column-gap-default"><div class="elementor-row"><div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-2d39fa8" data-element_type="column" data-id="2d39fa8" data-settings="{"background_background":"gradient"}"><div class="elementor-column-wrap elementor-element-populated"><div class="elementor-background-overlay"></div><div class="elementor-widget-wrap"><div class="elementor-element elementor-element-87a745b elementor-position-right elementor-vertical-align-middle elementor-view-default elementor-mobile-position-top elementor-widget elementor-widget-icon-box" data-element_type="widget" data-id="87a745b" data-settings="{"ekit_we_effect_on":"none"}" data-widget_type="icon-box.default"><div class="elementor-widget-container"><div class="elementor-icon-box-wrapper"><div class="elementor-icon-box-icon"> <span class="elementor-icon elementor-animation-">  </span> </div><div class="elementor-icon-box-content"> <span> **Free Checklist:** Hacker's Learning Path </span>

 Offline checklist to track your learning path, become a great hacker and stay on task.

 </div> </div> </div> </div><div class="elementor-element elementor-element-96a5f87 elementor-tablet-button-align-stretch elementor-button-align-stretch elementor-widget elementor-widget-form" data-element_type="widget" data-id="96a5f87" data-settings="{"button_width":"25","step_next_label":"Next","step_previous_label":"Previous","step_type":"number_text","step_icon_shape":"circle","ekit_we_effect_on":"none"}" data-widget_type="form.default"><div class="elementor-widget-container"> <form class="elementor-form" method="post" name="CTA - Hackers Checklist"> <input name="post_id" type="hidden" value="5269"></input> <input name="form_id" type="hidden" value="96a5f87"></input> <input name="referer_title" type="hidden" value=""></input><div class="elementor-form-fields-wrapper elementor-labels-"><div class="elementor-field-type-email elementor-field-group elementor-column elementor-field-group-email elementor-col-75 elementor-md-80 elementor-field-required"> <label class="elementor-field-label elementor-screen-only" for="form-field-email"> Email </label> <input aria-required="true" class="elementor-field elementor-size-xs  elementor-field-textual" id="form-field-email" name="form_fields[email]" placeholder="Enter Email Here" required="required" size="1" type="email"></input> </div><div class="elementor-field-group elementor-column elementor-field-type-submit elementor-col-25 e-form__buttons"> <button class="elementor-button elementor-size-xs" type="submit"> <span> <span class=" elementor-button-icon"> </span> <span class="elementor-button-text">Get</span> </span> </button> </div> </div> </form> </div> </div> </div> </div> </div> </div> </div> </section> </div> </div> </div> </div> </div> </section> </div> </div>Make sure you read over all the information, great, now let’s go over the questions.

- ‘What networking constructs are used to direct traffic to the right application on a server?’ – they’re numbers, starts with p.
- ‘How many of these are available on any network-enabled computer?’ – make sure to search ‘[Computer Networking Ports](https://en.wikipedia.org/wiki/Port_(computer_networking))’ for more help.
- ‘\[Research\] How many of these are considered “well-known”? (These are the “standard” numbers mentioned in the task)’ – searching will also help with this question too, don’t forget to count 0… no it’s not 1023.

## Task 3 Nmap Switches

Alright, next up, let’s learn about the various settings we can turn on and off, aka switches. Nmap has a lot of switches, so don’t feel discouraged if you can’t remember them all, it takes time. Don’t forget to read the `man` pages for `nmap` when you get stuck.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuzRqvx/ec1fb70d-2d55-4f8e-a587-bfc91cd5ece7.jpeg?v=fcdfcbc8fea846989693610d9ef1f96d](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuzRqvx/ec1fb70d-2d55-4f8e-a587-bfc91cd5ece7.jpeg?v=fcdfcbc8fea846989693610d9ef1f96d)</figure>To save time, search through the `--help` menu to find switches with `nmap --help | grep "<search-term>"`.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/9Zum2dOr/82dba93f-c73a-4b38-95f3-1dd4117f9946.jpeg?v=d6b18cd51591a93262ef431007e23446](https://p146.p4.n0.cdn.getcloudapp.com/items/9Zum2dOr/82dba93f-c73a-4b38-95f3-1dd4117f9946.jpeg?v=d6b18cd51591a93262ef431007e23446)</figure>After you’ve gone through the info, let’s go over the questions:

- ‘What is the first switch listed in the help menu for a ‘Syn Scan’ (more on this later!)?’ `-sS`
- ‘Which switch would you use for a “UDP scan”?’ `-sU`
- ‘If you wanted to detect which operating system the target is running on, which switch would you use?’ `-O`
- ‘Nmap provides a switch to detect the version of the services running on the target. What is this switch?’ `-sV`
- ‘The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?’ `-v`
- ‘Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two? (Note: it’s highly advisable to always use at least this option)’ `-vv`
- ‘What switch would you use to save the nmap results in three major formats?’ `-oA`
- ‘What switch would you use to save the nmap results in a “normal” format?’ `-oN`
- ‘A very useful output format: how would you save results in a “grepable” format?’ `-oG`
- ‘How would you activate this setting?’ `-A`
- ‘How would you set the timing template to level 5?’ `-T5`
- ‘How would you tell nmap to only scan port 80?’ `-p 80`
- ‘How would you tell nmap to scan ports 1000-1500?’ `-p 1000-1500`
- ‘How would you tell nmap to scan all ports?’ `-p-`
- ‘How would you activate a script from the nmap scripting library (lots more on this later!)?’ `--script`
- ‘How would you activate all of the scripts in the “vuln” category?’ `--script=vuln`

## Task 5 Scan Types TCP Connect Scans

Ah, TCP Scans, the default for `nmap` without `root` privs, make sure to go over the three-way handshake from the info provided. Let’s answer the questions:

- ‘Which RFC defines the appropriate behaviour for the TCP protocol?’ – RFC 793
- ‘If a port is closed, which flag should the server send back to indicate this?’ – `RST`

## Task 6 Scan Types SYN Scans

Cool, now SYN Scans, the default for `nmap` WITH `root` privs, let’s see the questions:

- ‘There are two other names for a SYN scan, what are they?’ – Half-Open, Stealth
- ‘Can Nmap use a SYN scan without Sudo permissions (Y/N)?’ – N

## Task 7 Scan Types UDP Scans

Lastly out of the main three scans, `UDP`, I’m still yet to really use this scan, but good to keep in the bank for later. Let’s see the questions:

- ‘If a UDP port doesn’t respond to an Nmap scan, what will it be marked as?’ – open|filtered
- ‘When a UDP port is closed, by convention the target should send back a “port unreachable” message. Which protocol would it use to do so?’ – `ICMP`

## Task 8 Scan Types NULL, FIN and Xmas

Next up is the lesser scans, ideally for firewall evasion as they’re a bit more complicated. After you read the info provided, here’s a look into the questions and answers:

- ‘Which of the three shown scan types uses the URG flag?’ – xmas
- ‘Why are NULL, FIN and Xmas scans generally used?’ – Firewall Evasion
- ‘Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?’ – Microsoft Windows

## Task 9 Scan Types ICMP Network Scanning

Ping sweeping, this is really good to remember! This is how you can find multiple hosts across a network, and fast. Use the `-sn` switch to enable it, and use arguments that specify the ip range and scope, see below for more. Don’t forget to run nmap’s help switch through grep to find the ping scan switch.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/E0ug7AQO/28b16547-928a-4412-aac3-ba65531d5263.jpeg?v=918c8b8665d07b8a9a1fe6d70b7510c3](https://p146.p4.n0.cdn.getcloudapp.com/items/E0ug7AQO/28b16547-928a-4412-aac3-ba65531d5263.jpeg?v=918c8b8665d07b8a9a1fe6d70b7510c3)</figure>Great, now let’s see the question for this task:

- ‘How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)’ – `nmap -sn 172.16.0.0/16`

## Task 10 NSE Scripts Overview

Scripts blow open `nmap` into a whole another level, some scripts go beyond enum into exploiting vulns, crazy. After going over the tasks, let’s tackle the questions:

- ‘What language are NSE scripts written in?’ – Lua
- ‘Which category of scripts would be a very bad idea to run in a production environment?’ – intrusive

## Task 11 NSE Scripts Working with the NSE

Great, use the `--script-help` switch to find a script’s help info, then go to the [info page](https://nmap.org/nsedoc/) for more.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/QwuLRAZj/163ba33b-725f-4675-bb72-059c314fd902.jpeg?v=a92661a9094392ee1a539d85260d4c8e](https://p146.p4.n0.cdn.getcloudapp.com/items/QwuLRAZj/163ba33b-725f-4675-bb72-059c314fd902.jpeg?v=a92661a9094392ee1a539d85260d4c8e)</figure>Here are this tasks questions:

- ‘What optional argument can the ftp-anon.nse script take?’ – maxlist

## Task 12 NSE Scripts Searching for Scripts

Learning `nmap` can be a bit tricky, now about the programs within the program, like I mentioned before, whole other level. Make sure to read all the info provided, take your time.

You can display Nmap’s database text file and search it using grep for “anon” as an example.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/kpuJoDqW/fd64c043-6ebd-49e0-be04-a58da493f7ea.jpeg?v=caf70bcef098feb366daf2127c0c8718](https://p146.p4.n0.cdn.getcloudapp.com/items/kpuJoDqW/fd64c043-6ebd-49e0-be04-a58da493f7ea.jpeg?v=caf70bcef098feb366daf2127c0c8718)</figure>Now try it again, but this time searching “smb”.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/2NuzRqNr/461f0b69-cfa9-4121-bb86-a562979a4843.jpeg?v=ee46ee4161cd31904a6efa5b536f9daa](https://p146.p4.n0.cdn.getcloudapp.com/items/2NuzRqNr/461f0b69-cfa9-4121-bb86-a562979a4843.jpeg?v=ee46ee4161cd31904a6efa5b536f9daa)</figure>Great, now let’s see the task questions:

- ‘Search for “smb” scripts in the /usr/share/nmap/scripts/ directory using either of the demonstrated methods. What is the filename of the script which determines the underlying OS of the SMB server?’ – `smb-os-discovery.nse`
- ‘Read through this script. What does it depend on?’ – `smb-brute`

## Task 13 Firewall Evasion

Now this may ring a bell, we’ve already touched on firewall evasion back in task 8, go back up if you need a quick refresher, I’ll wait. Search nmap’s help again, this time search for “append”.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRwPjw/1b2a5018-f6a9-418f-9aad-509c3c0123dc.jpeg?v=76768cc239319351ebc56900f1d1c455](https://p146.p4.n0.cdn.getcloudapp.com/items/nOuRwPjw/1b2a5018-f6a9-418f-9aad-509c3c0123dc.jpeg?v=76768cc239319351ebc56900f1d1c455)</figure>Then again for “random”.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/d5u94AZl/b889235d-5484-4625-96c6-13aa1dc75c44.jpeg?v=71d3637e797ea666bac27f562601f004](https://p146.p4.n0.cdn.getcloudapp.com/items/d5u94AZl/b889235d-5484-4625-96c6-13aa1dc75c44.jpeg?v=71d3637e797ea666bac27f562601f004)</figure>Use the screenshots to help you with this rooms questions:

- ‘Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the -Pn switch?’ – `ICMP`
- ‘\[Research\] Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?’ – `--data-length`

## Task 14 Practical

Great, now you’re nearly at the end of the room, just the last practical nmap task. Use a Xmas scan, don’t forget to use the `-vv` to see talkative `nmap` results.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/4guKbndZ/1e1cbff6-c449-4a3b-aebe-39c5dfaa3d9b.jpeg?v=96a8802cbe5cfdae661159ffa0adfd88](https://p146.p4.n0.cdn.getcloudapp.com/items/4guKbndZ/1e1cbff6-c449-4a3b-aebe-39c5dfaa3d9b.jpeg?v=96a8802cbe5cfdae661159ffa0adfd88)</figure>You can increase the number of ports that `nmap` will target, looking back, maybe it’s better to use the `-p-` to scan all ports from the first scan.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/5zuLmYQo/86334718-cc78-4900-8480-e4ceabb02690.jpeg?v=a6e3d7a5ddd04ab6aa6c18b2496986c9](https://p146.p4.n0.cdn.getcloudapp.com/items/5zuLmYQo/86334718-cc78-4900-8480-e4ceabb02690.jpeg?v=a6e3d7a5ddd04ab6aa6c18b2496986c9)</figure>After your scan has finished, take note of the ports found.

<figure class="wp-block-image">![https://p146.p4.n0.cdn.getcloudapp.com/items/d5u94Aml/ff1d1299-90a0-4c38-8d8e-6cc0ac3f17fe.jpeg?v=facc8c5819f21c52455f24df9ff94e4d](https://p146.p4.n0.cdn.getcloudapp.com/items/d5u94Aml/ff1d1299-90a0-4c38-8d8e-6cc0ac3f17fe.jpeg?v=facc8c5819f21c52455f24df9ff94e4d)</figure>Once you’re happy with your `nmap` scan results, let’s go over the questions:

- ‘Does the target &lt;ip&gt; respond to ICMP (ping) requests (Y/N)?’ – `N`
- ‘Perform an Xmas scan on the first 999 ports of the target — how many ports are shown to be open or filtered?’ – `999`
- ‘There is a reason given for this — what is it? Note: The answer will be in your scan results. Think carefully about which switches to use — and read the hint before asking for help!’ – No Response.
- ‘Perform a TCP SYN scan on the first 5000 ports of the target — how many ports are shown to be open?’ – 5.
- ‘Deploy the ftp-anon script against the box. Can Nmap login successfully to the FTP server on port 21? (Y/N)’ – Y.

Great work, that’s the Nmap Room from TryHackMe, I hope you enjoyed it! If you have any feedback, please reach out to let me know.

This is Day 38 and 41 of [\#100DaysOfHacking](https://mrash.co/100daysofhacking/), subscribe to my [newsletter](https://go.mrash.co/newsletter) to see the CyberSec journey! If you like, follow my [Learning Path](https://mrash.co/learning-path-for-beginner-hacker/) for yourself, happy hacking.