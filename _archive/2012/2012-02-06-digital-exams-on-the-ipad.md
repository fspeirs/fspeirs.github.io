---
title: "Digital Exams on the iPad"
date: "2012-02-06"
summary: ""
layout: archive
---

It's prelim week at Cedars. In Scotland, pupils with additional needs can use a “Digital Question Paper” to complete their exam.

A DQP is a PDF with embedded forms. The pupil sits at a computer and fills in the form to answer the questions. For exams involving graphs, equations or other hard-to-do-on-the-computer things, they can also switch to working on paper. At the end of the exam, the PDF is printed out and the exam goes away on paper with the rest to be marked.

So this week it's been my job to get this going. I thought it would be useful to write down the process and considerations for doing this on our computer infrastructure.

Can you do this on an iPad? Of course you can.

### The PDF Bit

The first consideration is how to complete a PDF form on an iPad. After trying a number of different PDF apps, I settled on [PDF Expert by Readdle](http://itunes.apple.com/gb/app/pdf-expert-fill-forms-annotate/id393316844?mt=8). PDF expert does a great job of annotating PDFs, completing forms and saving, emailing and printing.

### Network Setup

I used the Timed Access feature of Airport Utility to blacklist the WiFi MAC addresses of the iPads we're using for the exams. The pupils don't know our WiFi password - at least they shoudn't; we deploy wifi settings by configuration profile - but blacklisting the MACs gives belt and braces security.

We don't have any other open wifi networks visible from within our school but it's always possible that a pupil could enable tethering on their iPhone before handing the phone over at the start of the exam.

We counter this by keeping the phones in another part of the school from the exam room and using Kismet to check for the appearance of new APs before the exam starts.

It would be very helpful if it were possible to disable connecting to arbitrary networks but that's not currently an option.

Because we need to print the papers at the end of the exam, we need some kind of networking capability so that the iPads can reach a networked printer.

I set up a Mac mini with an ethernet connection to a printer. I then had the Mac create a wifi network and installed Printopia to make the printer visible to AirPrint. This worked well enough but I found that the iPads occasionally failed to reconnect to the ad-hoc network after sleep. In future, I'll use a real Airport base station for this.

The Mac mini had no connection to the Internet and was freshly reinstalled so that no additional software or content was available and all network services were off - apart from Printopia and the ad-hoc wifi network.

### Network Security

Whenever we talk about using computers in exams, the question of data security and computer isolation comes up. I went through this in some detail and tried to lock down the iPads we're using for the exams as far as possible.

Here's what I did.

Firstly, take an iPad and restore it to factory settings. We used spare iPads for this but you could equally back up and erase the pupil's own iPad for the duration of the exams.

Next, install PDF Expert from the App Store.

At this point, I put together a configuration profile for exam iPads and installed it via iPhone Configuration Utility. In the profile, I turned off the following (and pretty much everything else I could turn off):

- Turn off Safari
- Turn off YouTube
- Turn off installing apps
- Turn off the iTunes store
- Turn off iCloud syncing, backup and Photo Stream

I set the profile to never be removable, which means you have to restore the device to remove the profile. Something that can't be done in the exam hall - at least, not without deleting the exam paper and the app too!

In addition, there is a setting in Settings > General > Restrictons that's useful. It's the "Allow changes" option for Accounts. You can't hide Mail via configuration as you can with Safari and YouTube but disabling "Allow changes" prevents the user from setting up a Mail account on the device.

Let's assume the worst: that, even with all the above in place, the pupil could still get access to the public Internet. If that happened, this device would still:

- be unable to surf the web, as Safari is disabled
- be unable to install any content from the App Store or iTunes because they are disabled
- be unable to receive any information by email because setting up email accounts is disabled

The only remaining vector for information is iMessage. It's currently not possible to completely disable iMessage by configuration, so you need to think about network defences.

Since we erased the iPads before we started, iMessage is unconfigured. In order to set up iMessage, the device must be able to sign in to iCloud and communicate with Apple's servers. Without access to the public internet, it's not possible for the iPads in the exam hall to be set up to communicate with each other.

### Attack Tree

Having done all this, I decided to develop an attack tree for cheating while doing exams on an iPad. The tree is below, but here's the minimum you would need to do:

1. Set up some kind of hotspot that Kismet can't detect in range of the exam hall
2. Connect to it during the exam
3. Sign in to iMessage
4. Relay each question to a knowledgable conspirator outside the exam hall
5. Receive each answer and paste it into the exam paper

…all without being detected by the invigilator. That's a pretty sophisticated, well-resourced and coordinated attack for a school pupil but I'm not deluding myself that such an attack is impossible. It's not. With proper invigilation it shouldn't be a problem but I would feel happier if iMessage could be disabled or if I could lock the device onto one network only. I may be over-thinking it a bit.

[![](http://farm8.staticflickr.com/7160/6831914815_352d29aea3_d.jpg)](http://www.flickr.com/photos/fraserspeirs/6831914815)

The purpose of exam invigilation is not to absolutely prevent any cheating. It's to prevent any _undetected_ cheating. The decision to make an attempt lies with the individual candidate and they should be detected and suffer the consequences.

At the same time, I'm defending this system against 15-18 year old kids from Greenock, not GCHQ and the NSA. It's important not to go overboard with the paranoia.

That's how we're doing Digital Question Papers on iPad.

(Please bear in mind that I am by no means a security expert and I don't claim that this analysis is bulletproof.)
