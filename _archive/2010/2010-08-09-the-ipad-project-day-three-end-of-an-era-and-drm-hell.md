---
title: "The iPad Project: Day Three - End of an Era, and DRM Hell"
date: "2010-08-09"
summary: ""
layout: archive
---

Today was a preparation day. The plan calls for the breakup of the iMac lab, so that's what I did this morning. It was a simple enough job to shuffle the computers into the various classes and hook them up.

Definitely gave me a moment's pause though. Where are all my beloved "computers" now? How will I teach "computing" without "computers"?

It's the end of an era, but the beginning of a new one. A new era in which computers serve the needs of children and teachers. An era in which computers are not special artifacts sequestered in a purpose-built chamber into which children are ushered in hushed tones to have their weekly audience with The Computers.

I'm optimistic but, still, .... my computers. _snif_

Let me explain what's happening: each class will have one iMac, to which they sync their iPads. The primary classes will all sync their iPads to one user account on the class iMac, so that they have as consistent an application set as possible.

The secondary pupils will all sync their iPad to their own user account on the iMac in their guidance classroom. This is because I want the device backups to be under the user's own control and not accessible to other users.

Now, let's talk about the App Store and app distribution. This is capital-H Hard and what I'm writing here isn't close to fully-formed yet.

The fundamental problem is that App Store purchases are tied to App Store accounts. Further, App Store purchases can only live on five Macs. This is a huge issue.

Here's the question: how do I make purchases from the App Store and get them onto 100+ iPads?

Here are the solutions I came up with. Bear in mind that a critical requirement is that pupils do not know the App Store account password. We don't want them spending our money!

### Solution #1: every pupil has their own App Store account on their own device

This is fraught with problems. For a start, every pupil needs a method of payment. Then you're paying for one license per iOS device, instead of once per iTunes account. Then there's the problem of making sure that everyone buys the correct application. Too much coordination effort.

### Solution #2: every class has their own App Store account

This might work OK for the primary classes, where everyone's syncing to one iTunes library. Won't work so well for secondary classes where everyone's syncing to their own iTunes library. When an app is purchased, everyone in the class would have to "fake-purchase" it for themselves to get it into their library. This will require a lot of running around typing in the App Store password to individual devices.

This solution leads to us buying one copy of the app per class. It's also annoying for secondary teachers who couldn't be sure that all their pupils all had access to some basic set of apps.

### Solution #3: one App Store account for the entire school

This might work, except that we would only be able to sync iPads to five computers in the whole school. This will probably be too much of a bottleneck. Having an iMac in the classroom that pupils can sync to is so much more convenient than having to get a time slot on the "sync computer".

### Solution #4: one App Store account for Primary, another for Secondary

This is the solution I'm going with at the moment. It, too, is rather fraught with hassle but is about the best that I could design. I have a Mac mini that will be the "canonical" computer for App Store purchases. Once bought on this machine, iTunes Home Sharing will make sure it appears on all the other machines.

This is agonising in many ways:

1. Every computer has to be authorised for one of two iTunes accounts.
2. For the secondary kids, every user account has to be individually authorised for the same iTunes account (i.e. telling the user's iTunes library that it's authorised for that App Store account).
3. Every user will have to check for updates individually, which requires a teacher entering the iTunes password.
4. This also costs bandwidth and storage. One update is downloaded and stored for each pupil.

### Non-Solution #5: iPhone Enterprise Program

I only mention this here because many people are sure to suggest it. It's not a solution to this problem, it's a solution to a different problem. My problem is "How to install 3rd party applications purchased from the App Store on a large number of iOS devices". The Enterprise Program solves the "How to install 1st party applications that we wrote in-house to all our employees' iOS devices".

The Enterprise Program says "You must be a company or organization with 500 or more employees and a DUNS number to apply". We don't have 500 employees (even counting the kids) and I have no idea what a DUNS number is. The only way the Enterprise Program helps me is if I can get an unsigned binary of every version of every application I want to deploy from the developer, sign it myself and deploy it to the devices. I can't see how that saves me any effort.

### The Ideal Solution

What I would really like to see is something a little like Mac OS X Server's Software Update Server.

Imagine that, instead of looking directly at the App Store, I could point (via a Configuration Profile) my iPads at an iTunes library on the local network containing authorised apps. The App Store app on the device would then only show apps that are available in that library and everything would appear to be "free" and could be installed directly on the device. Updates would appear on the device when the version in the master iTunes library was later than the version on the device.

### Pain

There is no way I can look at this that doesn't suggest to me that this is going to be the most agonising part of the entire project. I just hope we can keep it tractable.

This is a hole in Apple's App Store infrastructure that the massive interest in iPads for education is exposing, in a way that the iPhone and iPod touch never did. One can hope that someone at Apple is looking at ways to solve it. If you're that person and are reading this, I would love to help you in any way I can.

\[_Update_" Here's a radar for the 'ideal solution' - rdar://problem/8288347\]
