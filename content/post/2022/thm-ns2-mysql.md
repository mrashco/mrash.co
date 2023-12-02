---
id: 5707
title: Network Services 2 P3 MySQL - TryHackMe Walkthrough
author: Mr Ash
type: "post"
published: 2022-07-19
lastUpdated: 2022-11-04
url: "/tyryhackme-network-services-2-p3-mysql/"
draft: true
image: 
categories: "['Hacking']"
---

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper"><iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" frameborder="0" height="450" loading="lazy" src="https://www.youtube.com/embed/cxwwEz7LJSA?feature=oembed" title="Network Services 2 TryHackMe Part 3 MySQL" width="800"></iframe></div></figure><div id="hs-embed-container" style="position:relative;display:flex;width:100%;height:600px;"><div id="hs-embed-placeholder" style="position:absolute;top:0;bottom:0;left:0;right:0;margin:10px;overflow:auto;font-size: 14px !important">## [ Network Services 2 TryHackMe Part 3 MySQL](https://www.happyscribe.com/?utm_source=embed-player&utm_term=e546c563873a48a096f4426be70407d8 "Network Services 2 TryHackMe Part 3 MySQL")

Welcome back to another video.

We are going to be doing Network Servicestwo, part three

enumerating exploiting more commonnetwork Services and misconfigs.

We’re up to task eight, nine and ten,

and we’ll finish off with elevenrounding out this whole thing.

Cool.

All right, let’s start off with taskeight, understanding MySQL.

Just before I do, got to remind you,

if you want a written write up,you can catch the link to that below.

If you’d like to subscribe or leavea comment, any feedback would be great.

With that being said,there was something else.

All part one and two are already posted,

so if you’d like them,check the links or cards.

Cool.Now, task eight understanding MySQL.

All right.

What is MySQL in the simplest definition,it is a relational database management

system based on structured querylanguage SQL too many acronyms?

Yes.Database.

A database is simply a persistentorganized collection of structured data.

RDBMS Relationship Database ManagementSystem is a software or service used

to create and manage databasesbased on a relational model.

The word relational just means

that the data stored in the dataset is organized as tables.

Cool.Good to know every table relates in

some way to each other’sprimary key or key factors.

So if you’ve done some like web

development and that thiswill sort of make sense.

I have been in the web design world,so more front end stuff.

So this is not that familiar for me.

So if you’re not that familiar with it,and cool if you are, please reach out.

Teach me some stuff.Cool.

MySQL is just a brand name,

one of the most popular softwareimplementations as we know it uses.

Maybe I didn’t know a client server model,

but how do this clientand server communicate?

They use a language specifically SQL.

Many other products such asPostgreSQL I have seen that.

I’m pretty sure my DaVinci Resolve,

My video editing software usesthat to store all the projects.

Microsoft SQL, does anybody use that?

Is that like really popular?

Probably lots of legacy systems?

I have no idea, I’m just guessinghave the word SQL in them.

The similar significance that the product

is utilizing the structuredquery language syntax.

All right, how does MySQL work?

MySQL

as a Relationship Database Managementsystem is made up of the server

and utility programs that helpin the administration of the databases.

The server handles all database

instructions like creating editing,accessing tables, takes managers and these

requests and communicatesthem to MySQL protocol.

Using the MySQL protocol,this whole process can be broken down

into three steps MySQL createsthe databases for storing,

manipulating data and definingthe relationship of each table.

Two clients make requests by makingspecific statements in SQL.

And then three, the server will respond

to the client with whateverinformation has been requested.

So I guess we’ll be learning about likeSQL injection where we can essentially

feed in something else and it willrespond back with whatever we ask.

So yeah, it’s crazy.

Really interesting.

So it runs it so it runs various platforms

like Linux, Windows,most commonly in the back end of databases

for prominent websites in forms of somecentral components in the lampstack,

which is something,something and something can’t remember,

which includes oh, here we go, linux,Apache, MySQL and PHP, obviously.

Just kidding, I know what a lampstack is.

Okay, so here are some resourcesthat explain technical so cool.

More stuff to read another time.

What type of software isMySQL and the full thing.

So we got relationaldatabase management system.

I bet I said relationshipwhen I said it fast, not can’t remember.

What language is MySQL based on?

So s and a Q and an L.

What communication model does MySQL use?

So I think it’s the same as the others,

which was the client server model,but I am prepared to be very wrong.

Wow, I am not.

What is a common application of MySQL?

A common application of MySQL.

This is another product of SQL, not MySQL.

What is a common application?

Maybe the Mic.

No, that wasn’t right.

It’s a common application.

I don’t remember reading an application.

Let’s just the only time the wordapplication has been used, a database.

So we got a database,

but that’s not really SQLmodel, but the user language specified.

The lampstack is implementationof MySQL, but not a database.

Bit of a stumper,

I’m not sure on that one.

Okay, what major social networkuses MySQL as their back end?

I actually remember this from when I wentthrough it was Facebook

and yeah, you can just look that upand you can find it pretty fast.

All right, what is a common application?

Oh my God.

I do not know.

Feel free to leave this video whileread everything again.

Back end database.

That’ll be it.

This trips me out.The term application trips me out because

I always think of like a reallyfront facing application.

But a database

is a program is an application too,so back end database, awesome.

I did forget to start that up.

So I’m going to press that now.

So that will take 60 seconds.

So we’re going to do another port scan

and we’re going to be tryingto find out some information.

But I’ll start reading and then wecan do a port scan once that’s up.

So before we begin, let’s deploy the room.

Give it some time.

MySQL is likely not going to be the first

point of call when getting initialinformation about the server.

You can as always and we have previoustasks attempt to brute force default

account passwords if you reallydon’t have any information.

However, in most CTF scenarios,

this is unlikely to be the avenueyou want to pursue the scenario.

Typically you will have gained someinitial credentials from enumerating other

services that you can then enumerateand exploit my SQL services

as this room focuses on exploitingand enumerating the network services.

For the sake of the scenario,

we’re going to assume that you havefound credentials, root and password.

Cool.So that’s just instead of them creating

a whole series of other steps that we haveto do to find root and password,

give it to us while enumeratingsubdomains on a web server.

After trying to log in against SSH,

unsuccessfully, you decideto try it against MySQL.

Cool.So requirements.

You’ll have MySQLinstalled on your system.

So let’s see if we havegoing to run MySQL.

Okay, we’re using Metasploit,

but we do have MySQL installed, so wecan just see that by coming up green.

So that’s cool.

So we do a quick port scan thistime around on our system.

So I’m just going to go Nmap this time.

I’m actually just going to get rid of this

PP because we’re essentiallybeing handed a lot of information.

So we need to do thisa little bit quicker.

So not going to scan all the ports,honestly.

Probably didn’t even need to dothe A for scripts and that.

So I’ve already got 3306,

and since it’s four digits,I’m assuming that’s what we’re after.

So I’m just going to let that runanyway and come over here.

So great.So let’s go MySQL H.

So we have an IP ratherpaste that in there the username.

So we’ve been given that username,which was root and then P.

Now it doesn’t say we have a password,

which was password commands G.

Cool.

So we’re not in aLinux shell or bash shell.

Rather we’re in MySQL this time around.

So I don’t know, thingslike terminal who am I?

Kind of work.

Different.

Okay, cool.

So our scan had finished anyway,so we can just cut that out and crap.

So we just got the MySQLon 3306 and the SSH.

So yeah.

All right, cool.

Okay, now we have ourlogin credentials work.

Let’s quit out of the section here.

So I’m just going to leave that inthe background and launch Metasploit.

So remember MSF console.

So we’re going to be usingMySQL underscore SQL module.

I’m just going to copy that and we’re

going to search for it and thensee if we can make sure if we’re going

to create a payload,we might be creating a payload to copy,

paste and execute hereto receive a reverse shell.

So we’ll see what the roomhas installed for us.

So when I search that, so we onlygot one option that matches it.

So we can copy that in and submit that.So we got that.

Cool.So hint is separated by things.

Yes.

So that’s not right.

So we don’t want the full auxiliary.

Is that what you’re after?

Okay, let’s just read this again.

Search for select list options.

What three options dowe need to set first?

Oh, sorry, it’s not asking us for that.

So let’s just use zero and let’sjust look up our options.

So we’ve got one, two, three.

So we’ve got our hosts.

We’re saying we might need to do other

ones like ourhosts password and then user.

Username.

That in order.

That was not in order.

Okay, so that’s what it wants.

Just sort of guessing there.

So we got to set the password,which we know is password when you set our

hosts IP,we don’t need to set the R port because

I assume that this is the default portjust because it’s the same here.

We don’t need to specify the versionof SQL even though it is required.

I guess there’s probably

let’s do this by specifying passwordand that will just be lower case password

and we’re going to set our hostand that’s going to be our IP.

So just paste that in to the system

that we’re looking at and then setuser name and that’s going to be root.

Okay, so we should just be able to go run.

But before I do that,

run the exploit by defaultto test with the select version command.

Wait.Did I misunderstand this?

Is this the SQL to execute?

I understand this is not asking

for a version, this is actuallyan SQL command that will be executed.

So if we run this, we should get back theversion that it’s running because it ran.

So we can essentially now run any SQL.

So we just need to find the right SQL.So what does it give us?

So it gave us this back.

Cool, great.

We know that our exploitis landing as planned.

Let’s try to gain someambitious information.

Change the SQL option to show databases,

set SQL to show databasesand then we’ll run it again.

And how many databases are returned?

So we’ve got 1234.

Cool.Let’s move over to our last task.

Task ten for exploitingMySQL So what do we know?

Let’s take a sanity check before movingon to try and exploit the database fully

and gain more sense of information on thedatabase than just the database names.

I just want to take a second because I do

really like how it’s sort ofbefore it’s teaching us

to really understand what we’redoing to enumerate and then exploit.

But I just like this last step before we

export exploit it’s just like justmake sure we’ve got everything.

I think this is going to be good foronce I’m more experienced down the track.

Just you get used to everything and it’sjust good to take your time, I guess.

MySQL server credentials.

So root password,the version of MySQL running.

So we’ve got that here.

And then the numberof databases and their names.

I’ve got idea.

So it’s probably I shouldreally be keeping a list.

Where is this?

So if we just change into documents here,

we might just create awhat did I call the last one?

I think I just call it MySQL Ssql.

And I’m just going to copysome of this information over.

So I should be doing thisa lot more basically.

But how do I undo?Was it alt?

Said no, can’t remember.

How alt a I can’t remember howto whatever, I’ll just leave it cool.

So that’s pretty much we need this.

And I mean, of course we’vegot root and then password.

I think I can remember that,but that’s kind of it.

So in my scale, physicallya schema is key terminology.

So we’re just goingto learn some key times.

Schema.

A schema is synonymous with the database.

You can substitute the keyword schemainstead of database in my SQL syntax,

for example, using create schemainstead of create database.

It’s important to understand

the relationship because some otherdatabases products draw a distinction.

For example, in the Oracle databaseproduct, a schema represents only a part

of a database, the tables and theobjects owned by a single user.

That’s really confusing.

I’ve never understoodschema, to be honest.

Like saying it’s like a database.

I’m like, okay, because I know like in SEO

world, like the Google and stuff, schemais important but never really got it.

Hashes.I have a little bit of understanding about

so very simple productof cryptographic algorithm.

A cryptographic algorithm to turn

a variable length into an inputfixed length output.

So in SQL, hashes can bevery in different ways.

For instance, an indexdata into a hash table.

Each unique hash has a unique ID thatserves as a pointer to the original data.

This creates an index that issignificantly smaller than the original

data, allowing the values to besearched and accessed more efficiently.

That’s interesting.

So I always associate hasheswith password, hashing and security.

But it also can just be used for a methodof searching and accessing efficiently.

However, the data we’re going to beextracting our password hashes,

which are simply a way of storingpasswords and not in plain text form.

Let’s start cracking.

All right, let’s searchfor my SQL schema dump module.

So we’ll go search paste that in there.

It should be the only one.

So we can just go use zero.

So we’ve selected our tool here, but it’sgoing to ask what is the full path?

We can just chuck that in there.

Great, now we’ve done a few times by now.

So let’s take it from here.

Set the relevant options, run the exploit.

What’s the name of the last database?

We don’t need to oh wait, no,it said set the relevant options.

Okay, so let’s have a set display.Results are true.

So we’re going to set password.

So that’s just going to be password set

our hosts, which is just goingto be our IP that we’re targeting.

And then set username,which is just going to be root.

That is our exploit machine set up.

So we can just hit run.

I guess schema dump is like database dump.

So it’s just going to try and findall the info from the databases.

What’s the name of the lasttable that gets dumped?

So when you’re looking for the last table

I don’t know if there’s likea verbose mode in Metasploit.

Going to save this off, by the way,

just so I got some stuff here.Yes.

Cool.Here we go.

Let’s have a good old scroll.

So there’s a lotI’m not going to scroll all the way

to the top, but we just wantthe name of the last table.

So table name.

So we’ve got here, I’m going to assume,

including X and paste that in therewaits global by latency.

So I have no idea whatthis SQL database is.

Awesome.

Now you have dumped tables and columns,names of the whole database.

But we can do better.

Let’s search and selectMySQL hash dump module.

Oh my gosh.

How many things are in thistool that we can use?

So what’s the module full name?

I’m sort of realizing there’sprobably like variables.

I keep seeing this.You can use variables.

I wonder if you can setlike a variable of IP.

So if I like, setour host to IP,

but I set this as my IP so I don’thave to copy paste this every time.

It’s probably much more efficient ways ofdoing everything that I do the wrong way.

Again.I’ll learn them eventually.

Again, I’ll let you take it from here.

Set the relevant options.

So let’s go up.

So we’ve got password.

So set password.

So that was password.

Cool.

Sorry.

What am I doing?

Set our host to this fella.

And then we want to setthe username username to root.

Cool.So that’s set up.

And then we should just be able to go run

and it’s going to say, cool,that was a lot faster.

So we’re getting users and hashes.

Well, that’s cool.

Hash dump is what?

Non default user stands out.

Carl.

Carl stands out.

So another user.

Another user.

Yeah, we got rudeand we have the password hash.

This could be very interesting.

Copy the hash to string,like full it’ll, copy this whole thing.

And we can just nano a fileand copy it in there.

But we can also echo this file.

Is that how that works?

That’s not how it works.

And paste it in here.

So we’ve got Carl and thenwe’ve got the hash.

So one is like bob and then the hash.

So we’ve got thatand I just called it hash.

Yeah.

So if we cut out hash, we’ve got this.

We’re going to use John the river.

So what is the user hash combination?

So we can justcopy that in there like so sweet.

Remember the hash col hash.Got it.

Okay, now we need to crack.

Let’s use John the Ripper against this.

It’s just saying John.

But I thought oh, really?

That was a lot easier.

I thought we need to use a wordlist.

I thought we needed to also usesomething else.

Cool.Awesome.

Password reuse is extremely dangerous,but extremely common.

What are the chances

that we can use a different service likeSSH because SSH was running.

So we can go Carl and we goat and we can log into this user.

Yes please.And then we can go.

D-O-G-G-I-E for doggie.

And we can log in, hopefully,

so we can cut out my SQL tax and wehave got our final flag puzzle.

Paste that in there and goover to task eleven.

We got some further reading, add to thelist and we can complete our final task.

Awesome.Good work.

We did it.Yeah.

So well done.Congrats.

That’s network services too.

We learned a lot from NFS SMTP to MySQL,

plus the Network Services one that we did,which is pretty awesome.

So lots of stuff here,so I hope you took some notes.

You’ve always got this videoto come back into if you’d like.

If you want to see more of this,please let me know.

Leave a comment if you want to subscribe.Awesome.

If you’d like to like the videoor dislike, totally up to you.

Either way, just let me know what you liketo dislike, would love some feedback.

If you have any comments that you like

to make, please go down below and there’llbe a playlist for all of my other

triathlon walkthroughs ifyou aren’t interested.

And don’t forget if you want a written

right up or you would like to subscribeto my newsletter,

I do have a good newsletter that I put outmonthly and that’ll be linked below too.

Cool.That being said, have a good day.

I’ll see you in the next one.

</div><div class="hs-embed" data-hide_video="true" data-id="e546c563873a48a096f4426be70407d8" data-private_text="true"></div><script>
var js=document.createElement('script');js.type='text/javascript';js.async=true;js.src='https://embed.happyscribe.co/main.js';document.head.appendChild(js);
</script></div><style type="text/css"> ._h1s512 { white-space: nowrap; } </style>