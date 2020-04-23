---
title: "Battle: Los Angeles"
date: "2013-10-01"
---

Last week was a bad week for iPad deployment. The students of Los Angeles Unified School District have "hacked" their school-provided iPads and figured out how to surf the web.

The horror! The horror!

The newspapers are, of course, all over this. The Los Angeles Times reports that students trivially worked around all the "security systems" in place and were using it for "unapproved purposes".

### The Technical Aspect

So what actually happened in LA? I don't know any details of the LAUSD deployment, but I'll give you my best guess and explain how this problem could have been avoided.

From the news reports, I infer that the deployment intention was to make the LA iPads be "education only" devices. There appears to be some educational content (from Pearson, natch) on the devices and the delivery of that content is the focus of their intended use at home.

The reports say that the effect of the "hack" was that students were able to surf the web, use Facebook, Instagram and Pandora. From this, I infer that LAUSD were using a configuration profile to disable Safari.

The [LA Times report](http://www.latimes.com/local/lanow/la-me-ln-lausd-ipad-hack-20130925,0,1971948,print.story) said that the students were "removing their personal profile" to bypass the controls:

> _"Roosevelt students matter-of-factly explained their technique Tuesday outside school. The trick, they said, was to delete their personal profile information. With the profile deleted, a student was free to surf."_

My best guess is that LAUSD enrolled the devices in an MDM server and then pushed out their restriction profiles over MDM. This is a mistake.

Under iOS 6 and - currently - iOS 7, an MDM enrolment profile cannot be set as non-removable. By design, the user _always_ has the ability to opt out of MDM control. Further, if a user does opt out of MDM control by removing the MDM enrolment profile, all the other profiles that were delivered through that channel are also removed.

So my best guess as to the nature of the LA "hack" was that the students went into Settings > General > Profiles and tapped "remove" on the LAUSD MDM profile. Some hack.

The technical lesson here is this: security critical profiles never come over MDM.

At Cedars, we use the Casper Suite from JAMF Software (disclosure: they also sponsor [my podcast](http://outofschool.net)). We deploy several configuration profiles over MDM but our base security profile is always deployed through Apple Configurator to ensure that students can't remove it.

This profile is quite simple and includes:

- Limit apps to 12+ rated
- Disable downloading of Movies and TV shows

These are the only settings that we enforce for every iPad and they're the only settings that we consider critical. I deployed them via Apple Configurator before opening day and they require a complex password to remove.

The rest of our profiles come out over MDM, with the full knowledge that the student could remove them. That said, we have ways and means of keeping kids on the straight and narrow.

Firstly, I have smart groups set up in Casper to alert me if a device hasn't checked in with the server in 48h. That strongly suggests that the device has been un-enrolled and should prompt some investigation.

I suspect LAUSD were also doing this as their CIO is quoted as saying "We knew immediately what had happened" by the [Los Angeles Daily News report](http://www.dailynews.com/technology/20130924/students-at-three-lausd-high-schools-access-unauthorized-sites-on-new-ipads).

Secondly, our Aerohive WiFi network integrates with Casper. When a device associates with the student SSID, it evaluates the MDM enrolment status of the device. If the device is not currently enrolled, it is denied access to the internet.

Finally, removing the MDM configuration is explicitly prohibited in our Acceptable Use Policy. That's no guarantee of good behaviour but it sets out rights, responsibilities and expectations clearly.

### The Social Aspect

Of course, there's a broader point to be made here too which is that an iPad that's locked down to Pearson curriculum content is probably the saddest of all iPads. The very act of giving out an iPad for "education only" purposes generates exactly the pressures that lead to breaches like this.

Imagine you're 14 and, one summer, you hear on the news that you're getting iPads when you go back to school. You go back, are handed an iPad, and then they tell you that you can't browse the web, can't use it for personal projects and all you can do with it is look at Pearson apps.

Total heartbreak.

If that was me, I think I would prefer that I had never had my hopes raised at all than to be presented with an iPad that, in the words of LA students quoted in the news "you can't do anything with them".

Early in our deployment, I realised that there was going to have to be some give and take with our iPad content. Yes, we deployed Angry Birds. We deployed several games. Some explicitly educational, others less obviously so. When you have as many wet playtimes as a Greenock school does, you're going to want some of that.

You know what the impact was, though? A dramatic drop in petty indiscipline cases. Those boring slack times in school could be filled with something useful or just plain fun. We found that, early on, pupils would just use free time to play games. As the deployment progressed, and the culture changed, pupils started to use the iPad more creatively in those times - either catching up on work, doing personal research or exploring new apps. It's not uncommon to see kids sitting before school or at lunchtime practicing with an app that they don't otherwise get much chance to use.

The point is that this is a programme of culture change, not just technical change. Some may criticise this as "giving out candy" in school but people are not rational and children doubly so. You can enforce obedience through technical means or you can use all the carrots, sticks, honey, sweets, jokes, cajoling and nudging that real, sustainable cultural shifts require to move your organisation to a better place.

Every change produces short-term spikes in petty abuse. We saw it this year when we allowed kids to install their own apps. Game playing increased again and we had some issues with kids playing games as the lesson began.

Did we immediately lock out the App Store and force everyone to delete their games? No. That's certainly a last-resort tactic that we _can_ deploy, but we sat everyone down and had a conversation about when it's appropriate to play games and when it's not. Critical to that conversation is the idea that there are _some_ appropriate times for relaxation, downtime and plain fun. Let children be children.

At the same time, another big part of that conversation is engendering the understanding among students that things could be very different if they don't play their part too. A mature culture recognises this and everyone knows that if we all play our part, we can have and continue to have something great in our school. If it all goes to hell and I have to bring the shutters down, that's going to be bad for everyone.

It's give and take. It can't be all take by the students or it's just chaos, but it can't be all take by the school either.

There is some hope in LA, though. Some of the follow-up articles quoted officals as saying that this "hack" provides an opportunity to talk to students about appropriate use. If that maturing conversation is what comes out of the LA Hack, that will be the best possible outcome.

We can only hope. As the most high-profile iPad deployment in the world right now, a lot rests on LAUSD getting it right. If it all goes wrong, I'm going to be apologising for it for years.
