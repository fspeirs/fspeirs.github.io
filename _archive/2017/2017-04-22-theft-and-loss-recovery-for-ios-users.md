---
title: "Theft and Loss Recovery for iOS Users"
date: "2017-04-12"
summary: ""
layout: archive
---

Recently, I took my family on a trip to France. We had a wonderful time but it was slightly marred by the events of the last evening in Paris when one of our bags was stolen from literally at our feet in a restaurant.

A number of things were lost but the most concerning one was my wife's iPhone. We were able to quickly disable her bank cards and her SIM card, so nothing serious was lost, except photographs, but the incident got me thinking about what I would do if my own devices were lost in this way.

Fortunately, the bag was stolen on the final day of the trip and not the first, otherwise we would have had serious problems throughout the holiday. This is another post for another time, but it's kind of shocking how crippling the loss of a phone is.

Certainly, the loss of the devices themselves is not trivial but the bigger concerns are (a) how to protect the data that is on those devices or accessible through them and (b) how to get back into my accounts and data in order to continue my trip.

### My Typical Setup

I use iOS devices and I use [1Password](http://1password.com) religiously. Every account I have is stored in 1Password and I have memorised _none_ of those passwords. I recently changed my Apple ID password to an unmemorable password (a mistake, as we shall see later), so the only password I have memorised is the one to unlock 1Password.

I use 1Password for Families, so my data is hosted by 1Password itself. I have 2-factor authentication turned on for every account that supports it, including my Apple ID, personal and work Google accounts, Dropbox, Evernote and others.

All my devices have passcodes. I use alphanumeric passcodes on my iOS devices. I have Touch ID enabled. My Apple Watch locks when I take it off. Find My iPhone is turned on for all devices and Activation Lock is enabled.

I'm really doing my best here. Ironically, though, it's this good level of security that makes the recovery trickier.

### My Disaster Scenario

Fortunately for us, only one device was lost in the random snatch of a single bag. For this post, though, I'm going to assume the absolute worst case scenario and, if I can work back from that, I can work back from anything less bad than that.

Let's say, for the sake of argument, that I'm walking down the street in a large city somewhere abroad and I'm approached and forcibly relieved of all the valuable possessions on my person. In a typical tech conference scenario, that would be my iPhone, iPad and Apple Watch all gone.

What now? Well, there are two phases to this: damage limitation and disaster recovery.

### Damage Limitation

The first concern is to limit the exposure of my data to attackers and Find My iPhone is the first place to go here.

Find My iPhone can be accessed through an app on another iOS device or on the web. Sensibly, you don't need to go through 2-factor authentication to get to this - I mean, you've just lost one of those factors - so you just need your iCloud password.

Here was my first problem: **I don't know my iCloud password**. It's long, it's random and it's stored in 1Password. So now I have to get into 1Password, just to send an erase command to my devices.

For me, that would take too long so my first task in this security audit is to change my password to something complex and long but still memorable without support.

Assuming I can get into Find My iPhone, the next thing I would do is put all my devices into Lost Mode. Lost Mode does a number of things but most importantly it disconnects any bank cards you have in Apple Pay from being used through any device in Lost Mode.

Lost Mode is actually better than immediately sending a remote wipe to your device. A wipe requires the device to be online to receive the command but Lost Mode will kill your Apple Pay in Apple's payment processing back end so you are immediately protected whether or not the device is online.

If you can see the device, then you might be in good shape to try and get it back. Many criminals, however, know to either turn off the iPhone or remove the SIM card, so it goes dark immediately. In my opinion, iOS devices should have locking SIM trays and require a password to shut down the device to close this loophole.

A point about getting devices back: I do _not_ recommend you just follow the map and try and find your device. Instead, hand this information over to law enforcement and let them chase the bad guys.

### Disaster Recovery - iCloud

So, assuming the worst happens and all your devices are gone forever - what now? Well, I need to get back into those accounts.

Let's assume that somehow I can acquire a new device. As a side issue, ask yourself how you would even do that. If everything was gone - how would you call home? How would you get money? Do you even have those numbers written down anywhere that isn't in your phone?

Also bear in mind that to activate an iPhone you might [also need a working SIM card](https://support.apple.com/en-gb/HT201407). I'm not sure if this is true everywhere on all networks, but I've certainly seen that requirement in the UK.

To sign into a new device, you need your iCloud password and a way to access your 2-factor information. With Apple's current implementation of 2-factor authentication, you can use a number of methods to get that second factor.

First, you can get it from another trusted device. This is when that dialog pops up and tells you that someone is trying to log in from a specific location, you tap OK and then you see a 6-digit code that you can provide.

Except in this scenario, all your trusted devices are gone. So that's out.

The next thing you can do is have a code sent to a trusted phone number. But your phone is gone and the SIM card is gone with it, so no calls or texts to that number.

Here, I discovered the second flaw in my setup. I only had my own devices set up as Trusted Devices and I only had one phone number set up as a Trusted Number - namely, my iPhone's phone number.

So, second task in this security audit: register a few other Trusted Numbers with Apple, and make sure that at least one of them is someone that you're not travelling with. Additionally, make sure you know how to get in touch with that person without access to any devices or iMessage or any social media.

It's also worth noting that, unlike most 2-factor authentication schemes, Apple no longer provides a "recovery key". Recovery keys for 2-factor authentication are like "safety net" keys that you can enter instead of getting a 2-factor authentication code from any of the usual channels. Google, Dropbox, et al. provide these kind of keys but Apple does not. Your only options are Trusted Devices, Trusted Phone Numbers or talking to Apple Support about getting back into your account.

### Disaster Recovery - 1Password

The last thing I need to do to get back up and running is to get into my 1Password database. I'm using 1Password for Families and I _do_ know my 1Password master password. However, that's not enough to get into 1Password.

1Password requires two pieces of information to get in: the master password and the account's Secret Key. When you are using 1Password for Families or Teams, you can create what is called a [1Password Emergency Kit](https://support.1password.com/emergency-kit/). This is a PDF that contains your 1Password Secret Key and your login information (but not your password). I wasn't carrying this, but I had it stored in ... a place that I couldn't get to without access to 1Password!

So, third to-do item in this process: print and carry a copy of my 1Password Recovery Kit. It's probably also wise to create a second copy and leave it with someone you trust and can contact, just in case you are stripped of literally everything.

### Wrap Up

With memorable passwords for iCloud and 1Password, and a copy of my 1Password Secret Key, I feel sure that I could get back to a working system from zero.

The to-do items for me that arose form this thought experiment:

1. Change my iCloud password to something memorable.
2. Register some additional Trusted Phone Numbers with Apple for my Apple ID.
3. Create a portable copy of my 1Password Emergency Kit.
4. Have methods of getting in touch with the owners of my other Trusted Phone Numbers if needed.

Certainly, what I have proposed here is the absolute worst case scenario I can think of that doesn't involve my being personally incapacitated or killed. Digital estate planning is a whole other consideration but the basics will be similar to what I have presented here.
