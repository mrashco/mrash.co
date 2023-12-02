---
id: 5725
title: TryHackMe Network Services 1 Part 2 Telnet
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5725
url: "/?p=5725"
---

Welcome to TryHackMe Network Services Walkthrough Part 2, oh yeah! Let’s learn, then enumerate and exploit a variety of network services and misconfigurations, second up is telnet. Watch this Network Services Walkthrough for TryHackMe’s room, Part 2 Telnet.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/_llaFR0354E?feature=oembed" title="TryHackMe Network Services 1 Part 2 Telnet" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:300px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ TryHackMe Network Services 1 Part 2 Telnet](https://www.happyscribe.com/?utm_source=embed-player&utm_term=e41dd55eff51408a9d95b18f998801c9 "TryHackMe Network Services 1 Part 2 Telnet was transcribed")

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
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>## Task 5 Understanding Telnet

Questions:

- What is Telnet? application protocol
- What has slowly replaced Telnet? ssh
- How would you connect to a Telnet server with the IP 10.10.10.3 on port 23? telnet 10.10.10.3 23
- The lack of what, means that all Telnet communication is in plaintext? encryption

## Task 6 Enumerating Telnet

Questions:

- How many ports are open on the target machine? 1
- What port is this? 8012
- This port is unassigned, but still lists the protocol it’s using, what protocol is this? tcp
- Now re-run the nmap scan, without the -p- tag, how many ports show up as open? 0
- Based on the title returned to us, what do we think this port could be used for? a backdoor
- Who could it belong to? Gathering possible usernames is an important step in enumeration. Skidy

## Task 7 Exploiting Telnet

Questions:

- Great! It’s an open telnet connection! What welcome message do we receive? SKIDY’S BACKDOOR.
- Let’s try executing some commands, do we get a return on any input we enter into the telnet session? (Y/N) N
- Now, use the command “ping \[local THM ip\] -c 1” through the telnet session to see if we’re able to execute system commands. Do we receive any pings? Note, you need to preface this with .RUN (Y/N) Y
- What word does the generated payload start with? mkfifo
- What would the command look like for the listening port we selected in our payload? nc -lvp 4444
- Success! What is the contents of flag.txt? THM{y0u\_\*\*\*\*\*\*\*\*\*\*}