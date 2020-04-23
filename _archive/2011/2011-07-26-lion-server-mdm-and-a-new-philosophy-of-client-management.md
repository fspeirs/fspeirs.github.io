---
title: "Lion Server, MDM and a New Philosophy of Client Management"
date: "2011-07-26"
summary: "This article is quite detailed and technical but I like it because I called a trend that 5-6 years later eventually arrived with DEP for Macs. Macs being managed like iOS devices."
layout: archive
---

I have recently been working on deploying a new server at school. Our old faithful Xserve G5 is coming to the end of its days and a new Mac Pro is replacing it. I decided to take the plunge and deploy Lion Server. There has been a fair amount of criticism of Lion Server but, for my needs, it is an outstanding release.

We have used Mac OS X Server at Cedars since 1999, when we went with that product over the then-current AppleShare IP. We use it for file sharing and client management - the so called Managed Clients for Mac OS X (MCX). Lion Server still supports the traditional MCX approach but includes a new feature called Profile Manager.

On iOS, client management has always been done via Configuration Profiles. A Configuration Profile is an XML file that defines settings in multiple “payloads”. For example, you might have two email payloads for two different accounts.

When we first deployed our iPads, the tool of choice was iPhone Configuration Utility. A Mac app that provided a friendly interface to generate and install Configuration Profiles onto devices over USB. You create the profile, plug in the iPad and click install. Bingo, your email, calendar, wifi and whatever are all set up. This was all fine until you need to change something - say, the WiFi password - then you’ve got to go and plug in every device and update the profile. You can send profiles to users over email but that’s not a great solution when your users are 5 years old. Thus, Mobile Device Management (or MDM) servers. An MDM server, essentially, lets you deliver profiles and updates to those profiles over the air (or OTA, as we say in the biz). MDM servers were not invented in the iOS era - they have existed in the past, mainly for enterprise management of BlackBerry handsets.

I looked into deploying an MDM server over the past year but, every time, I found that the pricing structures of these systems was much more closely aligned with an enterprise managing 5,000 BlackBerries than a school. We’re talking multiple thousands of Euro per server _plus_ a per-client charge.

Put simply, Profile Manager is an MDM server built into Lion Server. Lion Server is $50 with no per-client fee. This is A Big Deal For Schools (and, presumably, quite an unfortunate big deal for competing MDM solutions). Now, instead of creating profiles in iPhone Configuration Utility, you do it through a web browser in Profile Manager. Instead of installing the profile over USB, you push it OTA.

The second thing you need to know is that this works with Lion clients. Instead of the traditional MCX approach, you now enrol your Macs in Profile Manager and push profile updates to them in the same way you do to iOS clients. This is quite a revolution in Mac client management.

Computers used to be rare things. Today they’re ubiquitous. Every professional has one; most have two and an increasing number of people have three or more. This feeds into what I perceive as a shift in Apple’s thinking around client management.

In the computer-scarce past, the institution purchased and owned the computer. The institution managed the computer and the institution controlled what happened on that computer.

In the computer-rich present and the even-richer future, I think that Apple’s looking towards a different model. The user of the device “owns” it. Whether they really purchase it themselves is somewhat beside the point. The idea is that the person who spends their days working with that device has control of it, and the institution can overlay certain policies on top to meet their requirements.

It seems to me it's this second model that Apple’s interested in. It also occurs to me that, if you want the first model of total control - imagine you’re deploying the customer management system for a bank - you might be much better served by pointing Chromebooks at a web app than deploying full computers. After all, most such utilitarian Windows systems these days are little more than glorified drivers for the IE6 rendering engine….but I digress.

So, Lion Server provides us with a new model of client management: lightweight policy enforcement in 1:1 deployments. The disruptive consumerisation of IT is well underway. It’s been happening for a while and we all need to understand the implications.

It’s important, too, to realise that policy enforcement on devices is only one half of the story - and it’s the half your teachers don’t care about. I’ve said before that teachers want a predictable, reliable platform on which to deliver learning. Deploying an MDM server might appear to make the “run what ya brung” model a viable option but your teachers don’t care that you can ensure that every device has a passcode or talks to your proxy. Your teachers care about the software. They care that they don’t have to cope with special cases for everyone’s device. Until the day dawns when all you need on the client is a web browser - not a future I personally anticipate with relish - you’re still going to have to think about a degree of standardisation.

What I’m observing here is that we are moving from standardising every byte on the hard drive to standardising on a common operating system with some common applications.
