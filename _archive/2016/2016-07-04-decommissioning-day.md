---
title: "Decommissioning Day"
date: "2016-07-04"
summary: "I always love the day when you get to re-work everything."
layout: archive
---

So the school holidays are finally here and every sysadmin knows that that means you can start ripping things apart with total abandon. It's the happiest day of the year!

This year, I have a number of jobs to do since its refresh year. The first task is to decommission all of the old devices.

As part of the hand-in this year, I deliberately made sure all the pupils had turned off Find my iPad in order to disable the Activation Lock. This mostly worked and only a few still had it enabled.

Next, I decided to unsupervise them from Apple Configurator. I had a number of quite large USB hubs so I connected them all at once and plugged in about 30 iPads. Configurator (we are still on 1.8 at this point) promptly fell over.

So I unsupervised them in smaller batches until all were done. One of the big problems at this point is that you're working with old Lightning cables, some of which might not work perfectly. Lots of occasional random failures.

Anyway, I got that done and it proved that the entire set was no longer activation locked and were erased. I found a few devices that claimed to be supervised but Configurator could not see them. I think this dates back to the bugs we encountered in the iOS 7 transition where some devices lost their supervision identities, but I didn't keep a detailed record of that time so can't be sure.

As a result, I ended up forcibly restoring about six devices. No big deal.

### El Capitan

Next step was to upgrade the Configurator machine from Yosemite and Configurator 1.8 to El Capitan and Configurator 2. At this point, several iPads were behind in their version of iOS. I left them that way because I figured that Configurator 2 might do a better job of upgrading multiple devices at once.

Unfortunately, at this point, the Mac decided to throw its disk. Cue a 2+ hour rebuilding process which was tedious but uneventful.

Fortunately, Configurator 2 was much better at handling multiple devices at once. I was then able to update 25 or so iPads at once without issue. Bradley and I have given Apple Configurator a hard time on the podcast over the years but AC2 is definitely much, much better than version 1.

### New MDM

Next thing I did was set up a new MDM. We have used Casper Suite for years now and I consider it the single non-negotiable thing about my iPad deployment practice. I genuinely couldn't live without it.

Our previous Casper instance predates the release of VPP Managed Distribution in the UK so it had a lot of cruft in it about coupon codes and such. Between that and the rise of Apple School Manager, I decided that it was worth the effort to set up a new MDM.

We host our MDM on Amazon EC2, so it was easy to throw up a new virtual machine and install Casper.

In the old MDM, I revoked all the apps from all the users. The quickest way to do this is to delete your VPP token from Settings > Global Management > VPP Accounts. This automatically revokes every VPP license you have assigned.

I re-uploaded the new VPP token to the new MDM server and once it all synced up, I had all my app licenses in the new server.

### App Deployment

In the early days of VPP, you had to assign each app to an individual Apple ID. Since iOS 9, you can assign to a device instead of a user. This seems to be a better approach for school 1:1 situations. In my research at school, I discovered that almost no pupils ever installed a school-provided app on a personal iOS device.

Device Assignment allows you to push an app directly to a device and pull it back at will. Apple ID assignment sometimes worked and sometimes didn't depending on various factors.

As a result, we are moving to device assignment for all student devices in the next deployment.

We are also switching to the Casper mobile app for access to self service. Previously, Casper's Self Service was a web clip. The native app, as well as being faster and more responsive also allows administrators to send push notifications to all or some iPads with the app installed.

Another thing we are doing this deployment is making more use of optional installs of apps. There are a certain set of apps we want to be everywhere all the time - iTunes U, Google Drive, Pages, Notability - and other apps that we have enough licenses for to make available to everyone but which everyone might not need. These second kinds of apps are going into Self Service and pupils can pull them onto their devices as required.

As we start to move towards Managed Apple IDs, we will be leaning more on optional installs through Self Service. This is because Managed Apple IDs cannot buy apps directly, so everything has to come through the MDM.

This actually provides an additional benefit in that you can deploy apps with any age rating. Previously, we had allowed students free access to the App Store, subject to a 12+ age rating. This posed a problem when certain apps we wanted to deploy were rated 17+, such as Amazon Workspaces. By the same token, there were some apps that we definitely didn't want that were rated below 12+ (Hi, Snapchat!) Now, with Device Assignment and Managed Apple IDs, we can deploy only the apps we want regardless of age rating.

Another question, though, is whether you even really need Managed Apple IDs. As far as I can see, you only really get two benefits from having a Managed Apple ID over just, well, not having an Apple ID at all.

Firstly, you can subscribe to iTunes U courses. This is obviously very important for secondary schools but much less important for primary schools.

Secondly, you get iCloud storage for backup and other uses. Right now, Managed Apple IDs are still limited to the same rather stingy 5GB that consumer Apple IDs are limited to. In a world where Google are throwing unlimited free storage at schools, this is starting to feel like a real pinch. In a Shared iPad world where you're expecting to be able to offload a student's entire data load to iCloud, I can't see how 5GB is sustainable.

Still, if you are not using Shared iPad and you have enough experience to know that catastrophic hardware failures are very rare, maybe you don't need iCloud storage.

Still, these are early days in our redeployment. There's definitely more work to do!
