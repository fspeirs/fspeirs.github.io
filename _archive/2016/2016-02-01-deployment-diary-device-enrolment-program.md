---
title: "Deployment Diary: Device Enrolment Program"
date: "2016-02-01"
summary: ""
layout: archive
---

At Cedars, we are now in our sixth year of being a 1:1 iPad school. We started in 2010 with the original iPad and refreshed in 2013 to the then-current 4th-generation iPad with Retina Display.

In summer 2016, we will be refreshing again to new hardware. As time has gone on and I've gathered more responsibilities at school, the time available to work on the redeployment has naturally reduced. As a result, I'm starting work on the refresh much sooner than I have in the past.

I'm turning over the blog to a "deployment diary" over the coming months and I'll be publishing notes on the steps I'm taking and the experiences I come across as we make the move to new hardware for 2016-17.

### Current Deployment

Our current deployment is 110 4th-generation retina iPads, 32GB. We manage our devices using the [Casper Suite](http://jamfsoftware.com) and we deploy apps using VPP.

Every student has an Apple ID. Secondary students have control of their own Apple ID and junior students have a device-generic Apple ID (i.e. The Apple ID is not personally identifying but tied to the asset number of their iPad.)

Students with their own Apple ID are allowed to install their own apps, subject to age restrictions.

All iPads are supervised through Apple Configurator. We deploy a "base profile" to all iPads through Configurator and deploy the remainder over the air via Casper.

### What's New for 2016

The thing that is new for our 2016 deployment that already exists is the Device Enrolment Program.

Briefly, DEP is an Apple program whereby school-owned iPads are connected to your school MDM server before you even receive them. As part of the first-run iOS setup assistant, the user is prompted to receive the configuration settings from the school MDM and apply them to the device. Even if the device is erased, it will still pick up the settings from your MDM on the next setup. Basically, you're hooking your MDM configuration directly into the iOS setup system.

This has the added benefit of being able to supervise your device over the air - which previously required a USB connection to Apple Configurator - and also of allowing administrators to enforce MDM enrolment. Under all previous deployment systems, the user was always able to remove their device from MDM control, thus removing all restrictions.

### First Steps in DEP

The Device Enrolment Program is a service you have to sign up for. There is also a verification process you must go through in order to be allowed to set up a DEP account. The verification process was a bit of a pinky swear though - I had to basically verbally tell the person at AppleCare that I would use DEP for good and not for evil.

In order to set up DEP, I needed the school's Apple Customer Number - which Apple sales people will also sometimes refer to as your SAP number. I got ours from the Business Team at our local Apple Store and they provided me a number that was six digits long.

This led to a day's worth of confusion as the DEP Enrolment Portal demanded a nine-digit number. After an hour on the phone explaining the problem to Apple Enterprise Support, I received a solution: pad it out with three leading zeroes! Oh well.

Still, that got us through to the pinky-swearing ceremony and after a 24h delay and another verification call to the school to see that I was who I said I was, we had a DEP account set up.

### What DEP is Like Inside

Turns out, DEP is not very exciting inside - especially when you have no new devices to enrol in DEP.

You have two parts to DEP: devices and MDM servers. You have to enrol your MDM server or servers in DEP, and then you assign devices to those servers.

The process of enrolling a server in DEP was quite straightforward. You first download a key from your server. Casper Suite makes this very easy in Settings > Global Management > Device Enrolment Program.

You then upload this key to the DEP portal and download a token which you then upload into your MDM server. This way, each server is authenticated with the other and they can communicate.

The process of adding new devices appears to be straightforward but I haven't done it yet! We have ordered two iPad minis to test both DEP and iOS 9.3 with. They haven't arrived yet but it seems that I can use the Apple order number or a list of serial numbers to register these with the DEP portal.

In the interim, I have set up a separate instance of my Casper Suite on a new Amazon EC2 server to test with DEP. I will be assigning my new test devices to that MDM server and later moving them over to our production MDM.

This is one of the nice features of DEP. You can have multiple MDM servers and you can move devices between them. Why would you do this? Well, you might be a school district purchasing devices centrally for scale but then you assign them internally to individual schools, each of which have their own MDM server.

I don't think that having a separate staging and production MDM is a sensible practice for normal production but I wanted to keep everything separate from our current working MDM installation for now - just in case.

The other thing you can do in DEP is create multiple administrator accounts if you have a larger team of people dealing with devices.

The ultimate goal of DEP is to have a zero-touch deployment. The idea that you could - at least in principle - hand a student a shrink-wrapped iPad box and tell them to go and get started is quite a compelling option.

Further, the security of knowing that these devices will always remain supervised and under MDM control is something that will be welcomed by many. I have not personally had a lot of difficulty with students removing MDM profiles but it has been a factor in certain other more troubled deployments.

Practically speaking, I don't know if I would actually try to do a zero-touch deployment. There are a couple of reasons why not. Firstly, I would like to be able to check that there are no Dead On Arrival devices in our deployed set. I typically have a checklist of mechanical things to verify on each device: is the screen OK? Are the switches working? Does the camera work? Does it charge? Apple does an excellent job of quality control but sometimes things slip through. In our last deployment, we found one iPad on which the camera simply did not work. We also found one case where the cut-out for the camera hole was not there. These little things can catch you out.

Another reason I would probably not go down the zero-touch route is that it might be difficult to handle all the packaging that would be produced in one day, given the space we have available.

Finally, the impact on the network of all of the school's iPads enrolling in MDM and downloading gigabytes of apps on the same day might be more than we can handle.

Maybe the message is "Here's your iPad - take it home and set it up there"!
