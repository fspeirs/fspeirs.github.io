---
title: "The iPad Project: Day Four - Activate the iPad!"
date: "2010-08-10"
---

If you've seen the movie "Hero", there's a scene where Jet Li and his opponent stand off and visualise the fight to come and then, with one blow, the fight is over. Well, that wasn't me today. No, today, I was more like Simon Pegg in Shaun of the Dead waving my cricket bat around wildly.

I was working on backups and device activation. Fortunately we're not deploying 3G iPads, so there's a certain level of activation complexity that I don't have to deal with.

### Backups

First order of business was backups. I suspect this is going to be critical for us, since drops and breakages will occur at some point. We're buying a couple of on-site spare machines so that we can do a kind of in-house Rapid Return To Service (RRTS) without having someone be iPadless for a couple of days while I get theirs up to the Apple Store and fixed.

It's great that Apple's device backup system is as comprehensive as it is. With a couple of clicks, I can take a new iPad and make it look identical to the user's last backup. This takes away a ton of worry and hassle about backing up the data from every device.

However, these questions remain: what's in an iPad backup, how big can an iPad backup get and how quickly does it change? I have some of the answers.

The answer to "what gets backed up" seems to be, simply, "everything that you didn't originally sync from your Mac". In other words, application binaries, movies, music and photos are not included in the backup file. That said, the contents of the "Saved Photos" album is backed up. If you're doing a lot of saving stuff to the Photos app (for example, by using [Viewfinder for iPad](http://bit.ly/cf-viewfinder), hem hem), the backup file will grow a bit bigger.

For a full explanation of everything that is in an iPad backup, check Apple's [support document HT4079](http://support.apple.com/kb/HT4079). It's interesting to note that paired BlueTooth devices and the keychain are only restored if you're restoring to the same iPad device as created the backup.

I nuked my own iPad and set it up as new. The first backup was about 1.2MB. Later I checked at home and my last "full backup" of my working device was 1.7GB. They can get pretty fat.

I'm planning to have everyone back up their iPad at least once a week. A few kids will back up each day during the 15-minute guidance assembly first thing in the morning. Most of the Macs used for syncing are mounting the user's home directory over WiFi, so I hope this doesn't overwhelm the network. As with everything, we'll see.

### Activation

I spent the afternoon looking at device configuration. The iPhone Configuration Utility lets you create "configuration profiles" that can be installed on a device to provide complete control over many aspects of the device's operation.

You can lock out things like installing apps, using Safari or YouTube and set content rating levels. It's similar to, but a bit more extensive than the parental controls available on iOS devices. In addition you can force some other settings on the device. I'll discuss some of the settings we're using:

- Passcodes will be set for each device, 5 minute auto-lock with a grace period of 15 minutes.
- We can set the school's WiFi network SSID and password via a configuration file. This is great because it means we don't have to disclose the WiFi password to the pupils.
- We're deploying their email settings in one click. Always fiddly to get right. I wish Google Apps would let me force IMAP on for all users in my domain.
- The pupils will be automatically subscribed to the school's public calendar and their private Google Calendar CalDAV will be set up.

Those are the main settings. I wrote an AppleScript to generate a configuration profile for each user which I'll share here once I've worked out the kinks.

There was a huge kink in the script: none of the configuration profiles worked. After about 90 minutes of fiddling, I discovered that iPhone Configuration Utility generated a different configuration for the same data depending on whether the profile was created by hand or by AppleScript. The problem was with the email server port fields. If you type the numbers by hand, they're represented as Integer properties in the profile (profiles are standard Apple Property Lists). If you set it via AppleScript, it's represented as a String.

I have yet to absolutely verify that this isn't the fault of my script. It only happens with the IMAP server port and not the SMTP port. I suspect the workaround will be to export the profiles to disk, do a bulk find and replace in BBEdit and then re-add them to iPhone Configuration Utility.

### Late Good News

Late in the day, the Apple Store team called to say that they should have the iPads in the store tomorrow and we'll get them the next day. We're also buying an Apple iPad Case for each device. I think they're a bit more expensive than they really ought to be but I've been using one since I got my 3G iPad and I think they're functionally quite good. I hope they're durable enough.
