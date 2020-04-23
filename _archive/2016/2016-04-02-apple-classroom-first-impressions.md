---
title: "Apple Classroom First Impressions"
date: "2016-04-02"
---

Yesterday, I got Apple Classroom up and running at school thanks to the release of Casper 9.9, which supports the new features of iOS 9.3. Here are some early impressions. I'll mostly focus on the technology and how well it works, rather than how effective it is for teaching since I've only had a day or so to play with it.

### What is Apple Classroom?

Firstly, Apple Classroom is not like [Google Classroom](https://classroom.google.com/). Google Classroom is roughly equivalent to Apple's iTunes U - a service that lets you share materials and content with students and receive, mark and grade assignments.

Apple Classroom is more like a basic [Apple Remote Desktop](http://www.apple.com/remotedesktop/) for iOS. Apple Remote Desktop (ARD) was a Mac app that allowed administrators to monitor and manipulate multiple Macs remotely over the network. ARD was mostly a sysadmin tool but occasionally teachers would get into using it because of its ability to monitor and lock computer screens in a lab scenario. ARD was really too complex for classroom use.

ARD was also able to gather and report statistics about Macs on the network. These included disk space usage, device identifiers and so on. In the iOS era, all of these functions are handled by your MDM server. Still, we have been missing the screen monitoring features of ARD in iOS since day one.

Apple Classroom brings the 'teacher features' of Apple Remote Desktop to iOS, and it's fantastic.

### Features of Apple Classroom

Apple Classroom can do a number of things with a class of iPads:

- Lock and unlock the iPad screens
- Navigate the iPads to a web page or a chapter in a book in iBooks
- Open an app on all devices
- View a device's screen remotely
- Initiate an AirPlay session between a single student device and the classroom Apple TV

These are all very useful capabilities! In a Shared iPad deployment, Apple Classroom can also assign a student to a specific iPad, log a student out of a shared iPad and reset the student's Managed Apple ID password (which is their login password to a shared iPad).

### Setting Up Apple Classroom

Classroom is powerful and it's obvious that it's not a capability that should be in the hands of just anyone in the school, so how do we deploy it correctly?

Firstly, Classroom is freely available from the App Store. Anyone can download it, but it does nothing until it is configured by an MDM server. Additionally, while the teacher's iPad does not need to be Supervised, the student iPads do. You can't use this to just wander around peeking at strangers' iPad screens.

Classroom configures itself automatically when your MDM server sends a Configuration Profile that contains an "Education Configuration" payload. This is a structure in a Configuration Profile that contains information about which teachers have which classes and which students are in those classes. This ensures that a teacher only sees those iPads that are actually in front of their class at any given time, instead of all the iPads on the network.

### The Apple Classroom Interface

 Classroom basically has two views: the My Classes and the in-class screen. My Classes is a very simple interface that lets you pick from a list.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459591979658-TZNV1WF7GUESJEWOZ4N8/ke17ZwdGBToddI8pDm48kCFk-HIRdy_z0PvxLbIWyiZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0hHMyhIh2kKzuOL3ydJCryATlbr7F0IkXnds7UKpW3RQaNFdLKPoDBdsSTFxf21lPQ/image.jpg)

The in-class screen is where all the action happens. The basic idea is controls at the top and groups below. The controls across the top of the screen - Open, Navigate, Lock and Screens - act on all the iPads in the currently selected group.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459592111178-PBJJNIUJYX5KXXQILRE6/ke17ZwdGBToddI8pDm48kCFk-HIRdy_z0PvxLbIWyiZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0hHMyhIh2kKzuOL3ydJCryATlbr7F0IkXnds7UKpW3RQaNFdLKPoDBdsSTFxf21lPQ/image.jpg)

This is really nice because you don't have to go through a Select All step before doing an operation like locking the class screens.

### Groups in Apple Classroom

Classroom creates a single group to start with: All. This contains all the devices that are in the class. The teacher can then create static groups as required - for example project teams. Note that the Boys and Girls group in my screenshot above are static groups; they're not default groups in Classroom.

Classroom also creates dynamic groups based on the apps currently in use by students in the class. You might see groups like "Safari (10)" and "Keynote (20)" where the numbers denote the number of students in those apps.

Unfortunately, though, Classroom only creates two dynamic groups and then creates an overflow item of "Other Apps". I think I would rather have the option to see all app groups but I understand how that could get complex in a large class doing diverse things.

Classroom also creates another dynamic group called "Low Battery" for devices that are below - I think - 20% on power.

The nice thing about groups is that you can use them as shortcuts to Lock, Navigate or Open items on certain students' devices.

### Opening Apps in Classroom

In order to open an app in Classroom, the teacher has to have that app on their iPad. The teacher is presented with a scrolling list of the apps installed on the teacher's device, and can pick one to launch on all the iPads in the current group.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459592239846-7RWM6E11242J8LH0AFRH/ke17ZwdGBToddI8pDm48kCFk-HIRdy_z0PvxLbIWyiZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0hHMyhIh2kKzuOL3ydJCryATlbr7F0IkXnds7UKpW3RQaNFdLKPoDBdsSTFxf21lPQ/image.jpg)

I have a couple of quibbles about this interface. Firstly, there's no way to filter through the apps. My iPad has 125 apps installed, so finding one can be a little tricky. There are four "Recents" slots at the top, which helps a bit.

Secondly, as is common with many Apple Education apps, this interface doesn't really care to dynamically resize for the available space on the screen. It is unreasonably frustrating to have to scroll a tiny area for dozens of screenfuls when I have all this screen space available.

Finally, there is no indication of which apps the students have available to them. The teacher is presented with all the teacher's apps - some or all of which will not be available to the pupils. Classroom actually handles this situation gracefully - by quickly failing with a useful error message - but it's rather pointless to provide the teacher with a list of hundreds of apps, only a few of which might be valid targets.

I would also like to be able to create shortcut buttons for launching frequently used apps. Most teachers will have a few that they use routinely - iTunes U is a great candidate - and having direct shortcuts for those would be helpful.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459592296801-D30IO8HK3G3VVBN4LM26/ke17ZwdGBToddI8pDm48kCFk-HIRdy_z0PvxLbIWyiZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0hHMyhIh2kKzuOL3ydJCryATlbr7F0IkXnds7UKpW3RQaNFdLKPoDBdsSTFxf21lPQ/image.jpg)

There is an option to lock the student into an app after launching it. This could be useful for a test situation. Classroom seems to do two things when you select this option: firstly it hides all other apps from the home screen. Secondly, it initiates a guided access session for that app.

I noticed a weird visual glitch on the home screen when coming out of this single app mode. All the apps came back but the folder icons were darkened as if apps were being reinstalled. They weren't but it looked that way.

One nicely thought-through workflow feature is that, once the teacher has launched an app on the students' iPads, a button is provided to "Open _app_ on this iPad" in case you're about to demonstrate it. This also works when navigating students to URLs.

### Navigating to URLs and Books in Classroom

The Navigate button provides two options: to launch a URL on all selected devices or to open a book to a specific chapter.

Launching URLs is fairly straightforward: the teacher is shown their Safari bookmarks and can pick one to launch on all iPads.

This feature is a bit limited however: there's no way to type or paste a URL straight into Classroom without bookmarking it first. There's also no way to take a URL that you're currently looking at in Safari and Navigate students to in Classroom without bookmarking it.

One can imagine that a Share Sheet action for Safari to send its current URL to Classroom might be in the works. It would also be nice to be able to pick from the currently-open Safari tabs and iTunes U URL materials right inside Classroom.

As with opening apps, navigating students' iPads to URLs is extremely fast. Less than two seconds to initiate the load on an entire class in my testing.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459592571910-YIX4B8JJUEZRN4GF1WTJ/ke17ZwdGBToddI8pDm48kCFk-HIRdy_z0PvxLbIWyiZ7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0hHMyhIh2kKzuOL3ydJCryATlbr7F0IkXnds7UKpW3RQaNFdLKPoDBdsSTFxf21lPQ/image.jpg)

Navigating to books is similarly slick. Inside classroom, the teacher can select any book they have in iBooks. Classroom then lets the teacher navigate the book's Table of Contents and pick a chapter to launch on the students' iPads. Unlike apps, if the student doesn't have the book installed, they will be directed to the iBookstore to get it.

### Monitoring and Viewing Screens

This is the feature that many teachers have been waiting for - the ability to monitor what is happening on the iPad screens in their classroom. I'm happy to say that it works quite effectively. Classroom does not monitor screens by default. There is a button at the top of the group view that lets you toggle between a student's image and their screen.

The screen thumbnail views are _tiny_ and do not dynamically adapt their size to fill the available space. In my class of 11, the screens didn't adapt to fill the space on my iPad Pro (_I know, and my diamond shoes are too tight as well_). I don't know if this is done for performance reasons - the clients only need send a tiny low-resolution screen grab - or its just that Classroom is 1.0, but I hope this can get better.

If needed, the teacher can take a single iPad into full-screen monitoring on the teacher iPad. This can be useful if the teacher's iPad is already on AirPlay and you just want to show a quick glance to the class of what someone is working on.

The frame-rate on the full screen view of a student iPad is not very high at all. I would estimate it as about 1-2 frames per second (not a typo). You won't help someone with their animation remotely but it's good enough for static content.

Students are always made aware that their screen is being monitored. The standard AirPlay blue status bar appears on each student's iPad when the teacher is viewing thumbnails of all screens or one individual screen. I wonder if this feature is implemented as device-to-device AirPlay?

I would have liked to have seen a new colour for the status bar as I discovered quickly that the students did not associate seeing the AirPlay status bar with meaning "my screen is being monitored". They just wondered why their iPad was AirPlaying and where it was sending their screen to. I think that should change.

\>

![image.jpg](https://images.squarespace-cdn.com/content/v1/5005914284aed5ec11c2d2e5/1459592452838-E06CQKDEEBB6H3KYFG0H/ke17ZwdGBToddI8pDm48kBZw6jF4_OvU-ddo_vwqGhp7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1Ub61YCrK70I7JIpWiI8ho4Yi1WvVNQtDE81xuRbL1MFKm0sD-Bab7E9MY8W31A7zMQ/image.jpg)

### Locking Screens with Classroom

Classroom's Screen Lock feature is very sensitively implemented. It is light security, perfectly appropriate for a classroom situation. I found locking and unlocking entire classes to be fast and reliable. It took about 1-2 seconds for the operation to complete across the classroom.

How secure is the screen lock? Well, when the device is locked, the home button is inactive. Sleeping and waking the iPad does not bypass the lock.

If the teacher's iPad loses connection to the student iPad, the student iPad will unlock within 20 seconds. I tested this by locking a student iPad and then turning off wifi and Bluetooth on the teacher iPad. If either of those radios goes down, the student iPad will auto-unlock.

I haven't tested this extensively but my sense is that this is designed to avoid the situation where one teacher locks the class, the bell goes and the class moves on to another teacher who can't then unlock the iPads. This also solves the problem of how to unlock the devices if the teacher's iPad runs out of power during the class. If the teacher leaves the class with their iPad, I assume that will mean the student devices would unlock as soon as the teacher's iPad is out of Bluetooth range. Also, if the student reboots their iPad, the lock is bypassed.

This clearly isn't designed to keep the FBI out. iOS has other features for that, as we know. It's light touch attention management (what a horrible phrase), but speed and reliability are key in school and Classroom certainly delivers on this.

### AirPlay and Apple Classroom

One other feature that Classroom supports is initiating AirPlay between a student device and an Apple TV. There is no special configuration required for this. Classroom does the usual AirPlay discovery and finds nearby Apple TVs. In my testing, I found this feature to be fast and reliable.

This may not be a feature that is very useful for teachers of older classes but I can see it being very useful in younger years.

### How to defeat Apple Classroom

The Achilles heel of Apple Classroom right now is its total reliance on Bluetooth. If you are a student, the simple way to hide from Classroom is simply to turn Bluetooth off. This results in a total defeat of the system and is clearly something that needs to be addressed in future configuration profile options.

Many pupils still believe that turning off Bluetooth saves battery - despite having been born years after the Ericsson T28i first taught people to skimp on Bluetooth - while all the time running their screen at 100% brightness. More teaching required, I suppose.

### But what about teaching and learning?

My aim here has been to cover the technical features of Classroom rather than major on its use in teaching situations. I've only had half a school day with it at this point, so it's too early to say what the utility of all these features will be.

I can see myself using the screen locking and URL launching features quite a bit with certain age groups. More than that, though, I think the awareness of current apps in use through Classroom will help greatly in keeping the honest people honest.
