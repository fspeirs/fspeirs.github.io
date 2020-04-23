---
title: "Reflections on Deployment Day 2016"
date: "2016-08-24"
summary: ""
layout: archive
---

So it's now been a week since we rolled out our latest iteration of 1:1 iPad at Cedars. What does it look like and how did it go?

### Deployment Design

My intention is always to do one three-year deployment, not three one-year deployments. My aim, which we achieved in the 2013 deployment, was that the iPads would go out and not come back to me until the end of the lease.

Our school is straight-through K-12, with a slight bias towards pupils in the Primary department. We decided on a split deployment this time - using iPad minis and 9.7" iPad Pros.

One interesting thing in the discussions about the device was that the name "iPad Pro" might have actually hindered the iPad a little. The idea of buying a "Pro" device for a five-year-old just seemed to absurd to fly when, in both previous deployments, we had purchased the lower-storage fastest iPad. First time round we had no choice, of course, but last time round we bought everyone a 32GB 9.7" iPad with Retina Display. This time, the younger kids got something smaller.

The devices are: 64GB iPad Mini 4 (31 units) and 32GB iPad Pro 9.7" (94 units). This leaves us 1 spare mini and 4 spare iPad Pros. That's 3-4% spare capacity, which is about right. We could probably get away with a bit less given our Mean Time To Repair (it's very quick with an Apple Store 25 minutes away), but it's good to have a couple of identical spares to test things like iOS 10, Shared iPad and so on.

We are deploying the minis to Primary 1-4 (US: K-3) and iPad Pro for everyone else. I have in the past expressed scepticism about the suitability of the iPad mini for younger users and their poorer fine motor skills. I had to abandon that opinion in the face of the weight of evidence that literally every child who had their own iPad had a mini and they were all getting on _just fine_ with it.

We are again using Casper Suite for our MDM, hosted on Amazon EC2. We have been very happy with this product for a couple of years now and there was absolutely no compelling reason to change.

### Deployment Changes from 2013-16

There are a number of new technologies coming together in the 2016 deployment that we have not used before.

Firstly, these are the first devices we have purchased since the Device Enrolment Program came to the UK. We are also switching to iOS 9's VPP device assignment from the older iOS 7-era user-assignment model for apps. The huge change of course is the migration to Managed Apple IDs - about which more later.

### Migrating to a new MDM Instance

As part of the deployment, I decided to migrate everything to a new instance of Casper Suite. Doing this was remarkably easy and basically involved these steps:

- Shut down our old EC2 instance
- Set up a new EC2 instance and install Casper Suite
- Reconnect the new MDM to DEP and VPP by uploading keys and tokens to the appropriate places.
- Assigning our DEP devices to the new server and setting it as the default server for new devices.

The main downside to doing this is that we were 2 years into a 3 year reserved instance on EC2 and we couldn't make a new instance of the type that we reserved (m1.small). We are running our new JSS on a t2.small EC2 instance right now and monitoring that before we buy a new reserved instance. In general, I would like to get our EC2 reserved instances lined up with our deployment cadence.

### Preparation before the Day

The preparatory stage went remarkably smoothly on the whole. Devices were delivered and it was the _coolest_ thing to be able to see and work with them in DEP while they were still sitting in a TNT loading dock.

Once the devices arrived and were unboxed, the next steps were to:

- Connect them 20 at a time to Apple Configurator
- Restore the devices to the latest version of iOS (they all came with 9.3.2 and 9.3.3 was then-current).
- Use Configurator to kick-start the DEP process.

The restore step is important. Configurator lets you update or restore. Recall that all iOS devices greater than 16GB come with a pre-installed set of apps from the App Store: iWork, iLife and iTunes U. These apps will of course be unmanaged when you get the devices into MDM. You can take them under management remotely but to do so you'd have to scope all those apps onto all those devices and then un-scope any you wanted gone. Easier, to my mind, to just press the other button in Configurator.

All of this preparation went fine, except we didn't have our iPad Pro cases yet. The 9.7" Pro is very similar to the iPad Air 2 but it's not the same and it's definitely not case-compatible. For one thing, there are four speakers on the Pro. Secondly, and more importantly, the iPad Pro is the first iPad with a flash. iPad Air cases partially occlude the flash, which would be a constant problem for indoor exposure metering in photography.

We had decided on the recommendation of many many schools to go with the STM Dux cases. The nomenclature for these cases is confusing when it comes to iPad Pro. The STM Dux case for non-Pro devices is a case with a rubber frame, plastic back and an integrated wraparound cover. The "Dux" for iPad Pro is basically that case without the cover - obviously to allow access to the Smart Connector. We wanted a wraparound case for all our devices. This, for iPads Pro, is called the "Dux Plus".

Still, we got the cases in time and it's all good. The cases seem very robust so far and have a very clever clear plastic panel over the back. Some class teachers have put labels under there to identify individual kids' iPads and they won't wear or peel off.

### Rollout Day

We rolled out class by class. We ran into a couple of issues where we jammed the wifi by - maybe - associating too many devices in a short period.

#### Managed Apple ID Process

Let's just say that the idea of having to use a Managed Apple ID was ... _not warmly welcomed_ by pupils used to free access to the App Store. It wasn't my decision to migrate everyone to a Managed ID, but I had to because of the limitations Apple has placed on iTunes U and Managed IDs.

As a result of this forced migration, a few issues arose. Firstly, I feel that the deployment lost a certain amount of enthusiasm amongst the older students who have had (mostly) free rein up to now. As a result, I'm deploying a range of 'lifestyle' apps for those kids to soften the blow.

Similarly, a few pupils had purchased apps in their school Apple IDs and now have no way back to using those apps on their school devices. Also, some pupils had depended on their iCloud Document syncing in Pages and Keynote instead of backing up to Google Drive. That can be recovered through iCloud.com on a desktop computer but...who has desktop computers any more? ;-)

The setup process as designed in our DEP pre-stage was:

1. Enter personal wifi password (school-set)
2. Enable Location Services
3. Enter Apple ID & Temporary Password
4. Chance Temporary password (requires entering temp password again, then school password twice)
5. Accept TrueTone display page
6. Get to home screen
7. Enter password for iPad passcode
8. Confirm password for iPad passcode
9. Enter password for Google Apps account

I could have controlled the last two steps by not pushing the profiles until later but that would have required interacting with the JSS console in front of the class, which I really didn't want to have to do.

Younger and less-able children were very, very confused by the process of resetting their password. The terms "Current", "New" and "Verify" were too terse to fully explain what they were expected to do.

The "set passcode" prompt and the "Google apps" password prompt were in a race condition so some pupils saw one appearing first then another overtaking it. This led to confusion because I had started explaining a step and then some pupils were presented with dialogs for a separate step.

Basically, this was just too much passwording. Enter the school-provided password five times and the temporary Apple ID password twice (and twice in two screens at that!). This would have been much better if we could have set the final password in Apple School Manager and not required a reset of the password as part of the login.

### App Installation

Once pupils had completed the setup, the devices needed a 'kick' in JSS to get them going. I'm not sure why. If I manually prompted the devices to update inventory, apps started getting installed. All devices had pending installations as they had been sitting in setup assistant for about 3 weeks. I didn't have to clear them manually, and probably the apps would have installed next time the devices uploaded inventory (within the next 24h). Unfortunately I needed action to happen in the class basically as soon as Setup Assistant was completed. It would be ideal if the device could signal the MDM "I'm ready now" - which I don't think it can.

App installations proceeded smoothly from there. Caching server worked wonderfully well and we barely touched the Internet the whole day.

I noticed that when a number of apps were being installed, no visual feedback was given on the home screen. The network activity spinner was active but no darkened icons were shown on screen. The apps just appeared once they had been downloaded and installed. Children, who are well used to the App Store, found this confusing and disconcerting.

Overall, though, I have been pretty pleased with the deployment. The network, MDM and caching server all performed very well for Day One.
