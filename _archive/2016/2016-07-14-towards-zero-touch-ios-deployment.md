---
title: "Towards Zero-Touch iOS Deployment"
date: "2016-07-14"
summary: ""
layout: archive
---

One of my goals for the next deployment is to, well, do it faster. The holy grail of iOS deployment is to "never touch the glass". That is, to engineer a system whereby the most you ever do to a device is put it in a case and plug it into a cable.

Is this realistic? Not entirely but, with Device Enrolment, I think we are very close.

Whether you can actually get there depends on what kind of state you want to deliver the devices to users in. There are three levels of 'preparation' that you can apply to a device:

- Unconfigured: this is the 'shrinkwrap option'. The device hasn't been touched since it was delivered. There's nothing on the device.
- Partially Configured: the device is enrolled in MDM and configuration profiles have been installed but no apps are installed.
- Fully Configured: the device is enrolled, configured and apps are installed.

The "Unconfigured" option is great for businesses, universities and maybe even high schools. Basically, any situation where the users are adult enough to work through the setup assistant, log in with an Apple ID and let the setup complete.

The Partially Configured option is a good idea for middle school or any other situation where you want to _guarantee_ that the user won't be able to use the device without certain security settings already in place.

The Fully Configured option is best for younger users or situations where the available bandwidth to install apps is not up to the task of many users installing lots of apps at the same time.

How can we deliver each of these scenarios with 'zero-touch'? Let's take a look.

### Bootstrapping the Device Enrolment Program

The Device Enrolment Program lets you connect your Apple Devices directly into your MDM server at setup. As soon as your device contacts Apple's activation servers, it's redirected to your MDM server to be enrolled.

The question is: you need WiFi to talk to the activation server, so how do you get your devices up on the WiFi network and enrolling without touching them?

Turns out Apple Configurator is your friend here. As part of the Prepare step, you can tell devices to begin "Automatic Enrolment". Essentially, this initiates a mass jump-start of your devices into DEP. They're brought up on the WiFi and Configurator starts off the Device Enrolment process.

What happens after that is up to your DEP server. You can set options there to skip various of the iOS setup assistant screens, for example. At the end of the DEP process, you will have an iPad that is enrolled in your MDM server and has all the Configuration Profiles installed.

What you don't have is apps installed. For that to happen, you have to complete the setup assistant on the device. In various scenarios, this might require some involvement with the end-user or it might not. Let's look at some of those scenarios.

### Zero-touch Unconfigured Deployment

This one is quite easy: basically don't do anything! In an Unconfigured deployment you can, in principle, hand out an iPad in a shrink-wrapped box and let the user do the rest.

There are a couple of caveats to this. Firstly, you can't guarantee that the device will be on any specific version of iOS. iPads often come out the box with quite surprisingly old versions of iOS. This isn't usually a problem except when you depend on certain features being available. In school situations, right now, you're going to want to ensure devices are on at least iOS 9.3 to take advantage of education-specific features.

If devices are in DEP, you can now force an iOS update from your MDM server, which might mitigate this problem if you don't absolutely depend on a certain iOS version from minute 1.

### Zero-touch Partially Configured Deployment

In some deployment situations, you need the actual end user to do some setup on the device. This is usually because you need the user to authenticate to some directory service. The two most common scenarios in iOS deployment are:

- Logging into an Active Directory account as part of MDM enrolment
- Logging into an Apple ID as part of iOS setup

The latter case is probably the most universal example. That said, in this current world where you can assign apps to devices rather than users, it's not necessarily the case that every iOS device needs to have an Apple ID.

If you do need an Apple ID on the device, Partially Configured Deployment may be your best bet.

In a Partially Configured situation, you can deliver the device to the end users such that:

- The device is enrolled in MDM
- The device has Configuration Profiles installed
- The iOS Setup Assistant has _not_ been completed
- No apps have been installed

In this scenario, you are using the MDM server's pre-stage features to design a setup experience for the user that might be much simpler than the standard out-of-the-box iOS setup experience.

In pre-stage, you can configure the Setup Assistant to skip several panes of settings, such as Siri, Apple Pay, Zoom and Terms and Conditions.

You can also skip the Apple ID login pane and the Restore from Backup pane, although you probably don't want to to this. In this scenario, you _need_ the user to enter Apple ID credentials.

If you are using Managed Apple ID, users are assigned a temporary password. This is where the user enters that password and creates their own permanent password.

The benefit of a partially-configured model is that you can guarantee that your security restrictions are in place before the user sees the home screen. The major drawback is that, once the users have completed the setup assistant, they have to wait for apps to be installed.

My current model is to push a very small number of apps to _every_ device automatically once they complete enrolment. The risk here is that the network takes a massive hit on the first day of school when everyone completes the enrolment at the same time and those apps all begin to push.

Two techniques can mitigate this problem: firstly, use Caching Server in Mac OS X Server. This will save your external bandwidth but may still kill your internal WiFi for a while.

The second technique is to stagger the roll-out of apps. I'm deliberately keeping my auto-install list very minimal: iTunes U, Pages, Keynote, Google Drive. Just enough to get up and running on day one. The remainder of the apps will all be made available for optional install through Casper Suite's Self Service app. This way, the pupils can install the apps they need when they need them.

A slight downside to this technique is that, when a pupil (or class) finds they need a huge app like iMovie or GarageBand, the wait might be quite long. What I _might_ do is add those two apps into the Auto-install list at some point _after_ opening day.

### Zero-touch Fully Configured Deployment

In any scenario where the end user doesn't have a lot of ability to configure the device, a Fully Configured deployment is appropriate. When might this be true? In schools, when you're dealing with younger users or users with additional learning needs. In other scenarios, when the user won't really "own" the device but just use specific apps - think public iOS kiosks, loaner devices at museums or other borrowed-use scenarios.

A fully-configured deployment is one where the devices are brought to the ready-to-use state by the sysadmin without the end user's involvement at all.

This scenario is relatively easy to implement. In most of these situations, the user does not need to have an Apple ID on the device and apps can be pushed directly to the device by MDM.

The sysadmin can use Apple Configurator to start the Device Enrolment Program running and then all that is required on each device is to complete whatever steps in the Setup Assistant are required for the scenario.

The one pane I still recommend everyone leave enabled is Location Services. The reason for this is that iOS uses location services to set its current time zone. If you block Location Services, the default time zone is US/Pacific and you can end up with incorrect clocks on your devices.

As with other scenarios, you can't actually get to literally zero-touch as you have to complete the setup assistant. However, you can get the rest done - apps and configuration profiles - over-the-air.

### Conclusion

Are we at zero-touch deployment yet for iOS devices? _Sort of._

We can do a zero-touch deployment if:

- End users are able to complete a simplified setup assistant by themselves
- Our network can handle the automatic app installations that happen when the devices complete setup
- We don't need to ensure a specific version of iOS on the devices

Here's what I'm going to do for my deployment:

- For the youngest users, who don't need an Apple ID, I will deliver a fully-configured device.
- For all other users, I'll be delivering a partially-configured device

One of the main reasons for doing partial-configuration instead of zero-configuration is that, right now, we want to be sure that everyone is on at least iOS 9.3. I don't know what OS our devices will come with, but we rather depend on some of those features right now. In future years, this might not be such a concern.

The second reason I want to do partially-configured deployment is that I want to assign specific devices to specific users before handing them out. That way, I can set up asset tagging and so on before the users get their devices. In an Unconfigured deployment, you have to have some way of connecting a user with the device they have enrolled. Usually, you would do this by making the user log into their Active Directory account before they enrol in MDM. We don't have AD, so we have to do this step by hand.

We're not totally at literal zero-touch deployment yet for all scenarios but we are very, very close.
