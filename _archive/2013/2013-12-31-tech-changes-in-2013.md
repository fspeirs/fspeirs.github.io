---
title: "Tech Changes in 2013"
date: "2013-12-31"
summary: "Reflections on changes in technology in 2013. Of note: this was the year we went serverless in school."
layout: archive
---

I'm not generally someone who likes to think much about what has passed. I prefer to look ahead as much as possible but I always like to reflect on what has happened and changed over the past year whenever the calendar turns over.

### MDM Became a Thing

Although I had used MDM in the past, 2013 was the year that we deployed it for real. I chose the Casper Suite from JAMF in early summer and, to be honest, the decision really came down to price.

Most schools use Meraki and Meraki's MDM service is free. Casper is not free but it was much cheaper than some alternatives that are trying to sell to former BlackBerry enterprises.

We deployed Casper and have been very happy with it ever since.

### Decommissioned OS X Server

2013 was the year in which we finally shut down our OS X Server. I had arrived at the point where I was running a server to provide file sharing and login services to exactly one Mac. What iOS hath wraught!

I have been administering Mac OS X Server since 1999, when it was basically NeXTSTEP with the Mac OS 9 platinum UI. OS X Server has really changed since those days. In particular, it's become far less of a separate product and more like an add-on to OS X client. It's also fallen dramatically in price: I think we used to pay something like £500 for a server license and now it's about £13 on the App Store.

I can't say I'll miss administering OS X Server. The world has moved away from the product I used to work with. Today, the world is not just one-user-per-computer but in reality many-computers-per-user and running labs of Macs for people to share just isn't the way the wider world works any more.

I think one of the most prescient articles I ever wrote was [about Lion Server and Profile Manager, back in 2011](http://www.speirs.org/blog/2011/7/26/lion-server-mdm-and-a-new-philosophy-of-client-management.html):

> _Computers used to be rare things. Today they’re ubiquitous. Every professional has one; most have two and an increasing number of people have three or more. This feeds into what I perceive as a shift in Apple’s thinking around client management._
> 
> _In the computer-scarce past, the institution purchased and owned the computer. The institution managed the computer and the institution controlled what happened on that computer._
> 
> _In the computer-rich present and the even-richer future, I think that Apple’s looking towards a different model. The user of the device “owns” it. Whether they really purchase it themselves is somewhat beside the point. The idea is that the person who spends their days working with that device has control of it, and the institution can overlay certain policies on top to meet their requirements._

On [our podcast](http://outofschool.net), Bradley and I have been banging this drum for some time: that MDM servers are a new core competency for administrators in large-scale mobile device deployments. 2013 was the year we really stepped over that divide at school and shut off the legacy systems.

### iOS 7

I find myself in the odd position of both loving and being disappointed in iOS 7. The user interface was a major change, obviously, but for the most part it only looks different. It doesn't work all that differently. Not really.

My biggest disappointment has been that the fundamentals of iOS haven't changed as much as I wanted them too. In ["The iOS 7 Power User Challenge"](http://www.speirs.org/blog/2013/5/6/the-ios-7-power-user-challenge.html), I outlined some of the changes that I think need to be made to iOS to enable more advanced use of the platform. We got two of them: AirDrop and some deeper external keyboard support. Two major requirements are still missing: round-tripping documents between apps and changing the default apps for certain tasks. I hope 2014 and iOS 8 will bring these.

### Google Drive

For me, Google Drive was the surprise package of 2013. We started investigating it around May, when we were looking for an offboard storage solution for data pupils generated on their iPads.

We looked at Dropbox, Evernote and Google Drive. We rejected Evernote because it had a 100MB-per-note limit and we knew that some files - particularly videos - would be bigger than that. We rejected Dropbox because each free account came with only 2GB storage and there was no real unified account management system other than "Dropbox for Teams", which was far more data than we needed and far too expensive.

That left Google Drive. We have been a Google Apps school for nearly six years now and when we realised that Google were offering (at the time) 5GB for free and already integrated with our school email accounts, we jumped on it. At the time, Google offered 5GB quota for Drive and 25GB for Gmail. None of our students even use a double-digit percentage of their Gmail quota but they can certainly eat up the Drive space. Not long after we started using it, Google unified the quotas to give 30GB shared across both services. Talk about Christmas in June!

Since then, I've started to experiment with Google Docs. It's been another surprise hit for me this year. It's not the best for making pretty documents but, if you need the collaboration aspect on some basic documents, it's killer.

### Chromebook Curious

I got curious enough about Chromebook this year to go out and buy one. To me, ChromeOS has always been a far more "pure-Google" product than the me-too Android and far more interesting.

Certainly ChromeOS, like the other young platforms iOS and Android, has its fair share of limitations and issues. However, if you're very document-centric and you're looking for a cheaper version of the Dell laptop you use to peck out Word documents, a Chromebook might be exactly what you need.

### Two-Factor Becomes a Factor

Another feature of 2013 was that two-factor authentication became a standard feature of my computing life. All the major online platforms I use support it - except Amazon, curiously.

I have also been pushing it out to staff at school. It has been interesting to observe that it's actually not that hard to understand for most people. Particularly in the UK, where we have had two-factor authentication ("chip and PIN") for debit and credit card transactions for years now, describing 2FA as "chip and PIN for your email" is about all the explanation most people need.

### Smartphones as Cloud Remotes

Another trend I've noticed is that my iPhone is becoming little more than a remote sensor and display for cloud services. The only data I have on my phone that doesn't automatically sync to or from some cloud services is the videos I shoot with the camera.

The iPad is a very different story. On the iPad I have a lot of data that is held there: iPhoto and iMovie projects, PDF documents and so on. It's very interesting to reflect on how this has changed for me. I can't exactly explain why yet but I think it's partly to do with the fact that the iPad, while not constantly with me like the iPhone, is still with me almost all the time. At some level, too, I think it has become much less socially awkward to pull out a tablet and refer to it in public. Three years ago, that was the epitome of showing off. Today, it's just what we do.

### iPads for Work

One thing I've been watching closely in 2013 is the prevalence of iPads in real-world workplaces. It's an issue I've long been interested in as one of the early criticisms of our iPad programme at school - and iPad in general - was that "real work" (i.e. "typing Word documents") required a "real" computer (i.e. a "computer with a plastic keyboard running Windows").

I've never really bought this theory, having worked my entire professional life never having seriously used a Windows PC for even a single day.

2013 was the year when I think the iPad research and development that's been going on at many major companies broke through the surface. Here are some examples, from my notes this year:

- [Balfour Beatty used iPad-based site drawings](http://www.citeworld.com/tablets/21639/balfour-beatty-dfw-airport-ipads) so that everyone is up to date on the current plans.
- BAA staff at Heathrow Airport carry an iPad mini in a custom shoulder-sling case to handle customer service on the move.
- [American Airlines pilots now fly with an iPad in the cockpit instead of their flight bag](http://hub.aa.com/en/nr/pressrelease/american-airlines-completes-electronic-flight-bag-implementation).
- I saw British Airways staff using iPads to handle passenger lists on various flights I took.
- Many TV programmes feature the presenters referring to iPads. Two examples in particular from this year: the BBC's Formula 1 and football coverage both featured iPads in use during broadcasts.
- At our local Pets At Home store, the staff use iPad minis to capture customer information and orders all around the store and transmit them to the point of sale system.
- Just last night, I went out for a curry with friends and the waiter took our orders on an iPad.

These are just the examples that come to mind

### Looking Forward

There are a couple of things I still hope for in 2014. Firstly, I hope that iOS 8 will bring more power-user features. I look forward to my carrier turning on their LTE service in my area (finally!).

Mostly, I hope that Apple will produce a larger-screen iPhone in 2014. I'm not buying another iPhone until I can get a bigger one. My experience with the iPad mini taught me that I don't want a small phone, a small tablet and a laptop. In fact, I want everything bigger: bigger phone, bigger tablet ... and actually no laptop at all.

Why a bigger phone? Well, I liked the iPad mini a lot but it wasn't small enough and it felt rather redundant with my iPhone: carry two iOS devices everywhere? Given that the phone has to be there at all times, wouldn't it make more sense to increase the capabilities of the phone, rather than keep the phone small and carry an 8" tablet for the bigger tasks? I made fun of large-screen Android phones in the past and I fully recant.

One of the most important things I wrote this year was "[Beyond Consumption vs. Creation](http://www.speirs.org/blog/2013/3/4/beyond-consumption-vs-creation.html)":

> _I feel that the consumption/creation split is far too simplistic a curve to grade these devices on. It recognises almost nothing about the user's task beyond whether it's an input task or an output task. There's far more subtlety that we can reach for._
> 
> _I'd like to propose a more useful pair of axes on which we can place these devices - smartphones, tablets and traditional PCs - than simply consumption/creation. I'd like to propose that we can look at the 'sweet spot' for each type of device along two axes: task complexity and task duration._


![Consumption vs Creation](/assets/ConsumptionCreation.png)

If you look at the chart on that page, what I'm really asking for is for the mobile devices to squeeze the desktop comptuers harder in both directions. They should be usable for more complex tasks and for longer periods. I bought the 128GB iPad Air this year and its combination of huge data storage and high performance really has opened up many new tasks that I would previously not have attempted on my 64GB iPad retina. To give just one example, I recently completed a project that required the capture, management and editing of over 40GB of 1080p video and I did it all on my iPad Air without an issue.

I can't get rid of my Mac just yet, but I feel that I'm now at the stage where I actively want to. I've taken several trips this year on which I've only taken my iPhone and iPad and guess what? Nothing terrible happened. I got the work done just fine without my Mac. That's still not possible for every task and at every point in the year but my use of the Mac is just going down and down and down and I'm totally OK with this.
