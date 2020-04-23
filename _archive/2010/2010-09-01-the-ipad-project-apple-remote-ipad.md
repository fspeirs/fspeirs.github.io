---
title: "The iPad Project: Apple Remote iPad"
date: "2010-09-01"
summary: ""
layout: archive
---

One of the applications I depend on every day in school is [Apple Remote Desktop](http://www.apple.com/remotedesktop/). Now, many people think of ARD as a kind of steroid-enhanced VNC app. It is that, but it's so much more. Please don't email me recommending VNC apps. I have them and use them but just looking at another machine's screen is only a part of the problem.

I wanted to write about what I feel the next generation of Apple Remote Desktop should look like, in a world where one is as likely to be administering iOS devices as Mac OS X computers.

What I want is a Mac OS X app - let's call it ARD 4 - that will let me both observe the screen of an iPad but also perform several administration functions of a similar nature to the kinds of things that ARD 3 can do for Mac OS X clients.

In case you're not familiar with ARD 3, here are some tasks I regularly do with it:

- Observing remote screens
- Using the list view to see who's logged on and where
- Using the list view to check that all machines are running the latest OS update.
- Performing a software inventory on remote machines.
- Firing off parallel command line operations on all machines (e.g. invoking softwareupdate(8) across the cluster).
- Logging out users who have left themselves logged in
- Installing package files
- Copying files to or from users' desktops.

Now, of course, not every operation maps directly to something you could do to an iPad but here are some operations I'd like:

### Find That iPad

Where's that iPad? Even though we're not using 3G iPads, it would be useful to at least know which iPads are in school and which are elsewhere - even if the 'elsewhere' can't be known.

### Push a Notification

The ability to push a notification to selected iPads would be awesome.

### Install an App

Our syncing infrastructure is working well but I'd like to be able to push an app out to devices.

### Observe the screen

It's oftentimes necessary to look at remote screens. To be able to see what's going on with someone's iPad would be invaluable, particularly if it could be combined with a two-way audio session. Also, the ability to save a snapshot of the screen to the admin computer.

### Run 'Update All' on a device

We are syncing devices regularly but can only do two or three devices in the morning guidance class (15 minutes). It would be really great to be able to fire off an App Store "Update All" on a bunch of iPads over lunchtime.

### Software Report

Because we're not able to sync all devices at one time, we sometimes run into the problem of everyone having a different set of apps, at least until everyone's synced their iPad. To be able to gather data about which devices have which apps would be very useful.

### Install and Remove Configuration Profiles

There are various techniques for doing this, but Apple doesn't provide an easy solution of their own. If I could push new and updated configuration profiles to devices without user intervention, that would be very useful.

### Battery Diagnostics

If you've ever taken an iPhone to an Apple Store, you might have seen that they have some really sophisticated battery diagnostics tools available at the genius bar. They can see the average time between recharges, how long charges are lasting and the number of cycles on each battery. To have those tools to hand would be great.
