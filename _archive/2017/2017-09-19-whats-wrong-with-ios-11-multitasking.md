---
title: "What’s Wrong With iOS 11/12 Multitasking"
date: "2019-03-10"
---

\[_Note: This is an old article I wrote but never published, in the hope that these issues would bave been fixed relatively quickly. I thought it would be an interesting historical note on the design issues that ultimately drove me away from using the iPad as my main computer. I originally write this in September 2017, so a few details may be different on iOS 12 but the basic design remains the same. FS._\]

iOS 11 represents a major step forward for iOS in many ways, most notably on the iPad. However I am concerned about two aspects of the design of iOS 11: the Home Screen and the Multitasking interface. I worry that many people are not going to understand this and, even if they do, will find it either too difficult or too confusing to use in daily operation.

In my own use of iOS 11, I have found the home screen and multitasking to be imprecise, frustrating and overall slow to use on a daily basis. I had hoped that something would click for me; that there was some aspect of the design that I wasn’t quite getting that would illuminate it all but I can’t find that insight.

### Home Screen

My difficulties begin with the home screen. In iOS 10, there were two things you could do with an icon: tap it to open or press and hold to rearrange.

In iOS 11, there are now four things you can do with an icon:

- Tap to open
- Tap longer to get the recents popover
- Tap a bit longer to drag
- Tap yet longer to rearrange

I have a number of problems with this.

### Tap Timing is Hard

Now that we have four operations that are essentially the exact same physical gesture but differentiated by the length of time the gesture is performed for, I am concerned that many users will become quite confused.

Teaching someone that you get a different effect by just holding _ever so slightly longer or shorter_ is a recipe for frustration. Many users will discover this for themselves but likely put the differing behavior down to bugs or some kind of magical-thinking “I don’t know what I did to get this”.

Further, younger and older users with variations in their fine motor skills will have some difficulty executing these different gestures in the correct amount of time.

In my experience of using iOS 11, I have found that I frequently make mode errors in the Home Screen. Sometimes, I don’t hold long enough to initiate a drag and the operation fails. Other times I hold too long and I get into rearrange mode instead of initiating the drag.

### Same Gestures, Different Results

Another issue with the current design of the home screen is that the same behaviors produce different results based on the mode you are in.

If you’re dragging a single app, tapping another app will launch it. If you’re dragging a single app in rearrange mode, tapping another app will add it to the drag pile.

This, combined with the ease of making a mode error between simple dragging and rearrange mode can lead to some maddening behaviours on the home screen.

Another aspect of this problem is that if you simply drag when you intended to rearrange, tapping another icon causes the entire operation to fail because you are transported out of the home screen and into the second app you tapped.

Conversely, if you wanted to drag and then tap a second app to multitask, you can sometimes find yourself in rearrange mode, adding to a drag pile. At this point there is nothing to do but abandon the drag and start over.

There are a number of what you might call “functional cliffs” in iOS 11 where making a simple error can cause an operation or a set-up interface to irrevocably collapse and require reconstruction.

A further example of this is accidentally adding an app to a drag pile -there’s no way to drop one.

### Frustration and Slowness

Think about iWork for iOS for a second. In early versions of those apps, you had to select an object, then wait, and then tap again in order to make the black edit bar appear over an object.

This made the interface slow at best - there was a built-in waiting period every single time you wanted to Cut or Animate an object - and more often than not error prone. If you tapped and then tapped again too quickly, instead of getting the edit bar, you would begin editing the text inside the shape.

Some time in the evolution of iWork this was changed so that the edit bar appears immediately on object selection. This dramatically improved the perceived speed of the interface and helped make iWork the delightful suite of tools it is today.

Unfortunately, the Home Screen in iOS 11 suffers from exactly the same problem that the early versions of iWork did: large variations in behaviour from tiny variations in user performance.

### Multitasking

My second area of concern in iOS 11 is the design of the multitasking interface.

I deeply appreciate many of the advances in iOS 11 multitasking, such as allowing 25/75, 50/50 and 75/25 splits; in-place swapping of apps and moveable Slide Over apps. These are all great enhancements.

However, as I use iOS 11 more, I find myself increasingly frustrated by the process of getting apps _into_ these multitasking spaces.

### Enforced Waiting

Firstly, let’s consider trying to set up split-screen multitasking. The simple and obvious way to do this is to access the Dock and drag an item from there into either side of the screen. This is what I sometimes think of as the “golden path” for multitasking.

I still have an issue with even this, though, as it requires several taps, swipes and waits just to set up:

- Swipe the Dock up (this sometimes requires _two_ swipes if the status bar is hidden)
- Tap and hold an app until it lifts off (wait)
- Drag to the edge of the screen
- Wait again
- Drop it

Still, slow as that is, it’s at least simple and understandable. The more difficult situation is where you want to split-screen with an app that is not in the Dock.

I have already had several very savvy iOS users tell me that they simply thought it wasn’t possible to multitask an app that wasn’t in the Dock.

I know that there are a number of ways to do this but none are very discoverable and some are very difficult to execute.

The first method:

- Go to the Home Screen
- Drag an app (with enforced pause)
- Use another hand/finger to get back to the first app
- Hover over side (another pause)
- Drop

This method has the fewest enforced pauses but is physically difficult to execute.

The “spotlight method”:

- Invoke Spotlight
- Search
- Drag the app to the edge of the screen (pause)
- Drop

This method is only possible if you have a physical keyboard attached and invoke Spotlight with Cmd-Space. Without a physical keyboard, there’s just no way to do this at all.

My main issue in pointing out all of these methods and the enforced waits is that the whole multitasking interface just constantly _feels slow_. It’s slow to find an app, it’s slow to get it into multitasking. Over the course of days, weeks and months all of these pauses will add up.

### The Golden Path and the Long Path

One of the other results of the “privileging” of apps in the Dock is that you often run into a situation where you try one method to get an app (via the Dock), fail, and have to restart down the other path.

I find myself doing this a lot:

- Desire another app
- Pull up Dock
- App is not in the Dock
- Home screen
- (follow one procedure for multitasking that app)

I have observed a number of friends on Twitter posting screenshots of their iOS 11 app arrangement which can probably best be described as “everything in the dock and a junk drawer folder at the end” just so they can be guaranteed that the first path to an app (going via the Dock) will always yield a result. This feels distinctly like a workaround.

I have adopted the “junk drawer” approach to app layout myself and it is still constantly annoying. To get to any app that’s not one of the top 13 that have made it into the dock, I have to:

- Swipe once (or twice) to get the Dock up
- Tap to open the folder
- Possibly swipe to a secondary page of the folder
- Tap the app or begin dragging it into multi-tasking

This is another reason why iOS 11 feels slow to me - there are short paths and long paths. Reliably deciding which path to take requires the user to develop and maintain a mental model of the state of the Dock and Home Screen.

People are working around this path-difference by forcing every app to be accessed through the tiny window of the Dock. This at least has the benefit of making all apps accessible through the same kind of path, but that path is tedious and slow.

### App Pairings

The iOS 11 idea of there being multiple split screens and switching between them is, initially, an interesting idea. In practice, I have found it quite difficult to make any practical use of and have already mostly abandoned it.

First of all, my experience as an iOS-only user is that we constantly freely mix and match applications at will to solve various problems throughout the day. It’s not at all clear to me that there exist multiple stable pairs of apps that should always stay together.

There appears to be a level of impedance mismatch between the Mac-like idea of “multiple spaces” and the iOS model of “apps not windows”. When I first started using iOS 11, I tried to identify certain apps that might work well together - Mail and Calendar - for example.

In practice I found that, too often, I needed to create arbitrary pairs of apps and this caused all my bespoke app pairings to be dismantled in the background. This gave me a sense of instability in the iOS 11 UI. Things I had built were being dismantled invisibility and they were not the way I had left them. This is another of these “functional cliffs” - a short term use of an app leads to the invisible dismantling of a pairing in the background.

Again, as with the perceived speed issues in the Home Screen, I’m talking here about _percieved_ stability. I’m not referring here to bugs but to conceptual structures in the UI that don’t survive my general use patterns on iOS.

Combining all of this with the idea that Cmd-Tab now switches between _spaces_ and not _apps_ means that the user has to build and maintain a mental model of the state of all the spaces and apps in order to reliably predict what is going to happen when they switch to another app.

As a result, I find myself using Cmd-Tab less and less. This is because, for any app I might want to use, I have to remember if it was paired with something else. If it was, Cmd-tabbing to it or launching it from Spotlight will cause both it and its buddy to come to the front, replacing everything I was doing.

If the app I want is not paired with another app and I launch it, the app will appear full screen - again replacing everything I was doing.

Therefore, if I want to work with two apps - but constantly varying one or other app as I go - I am forced to use one of the dragging methods (Dock, Home Screen or Spotlight).

To me, this is one of the reasons why iOS 11 constantly feels slow: I spend too much time thinking about what the effect of certain actions might be and then I end up forced down one of the slower paths for rearranging my workspace - dragging.

### Losing Apps

Another “functional cliff” that I’ve come across is the behaviour of split screen multitasking when you entirely collapse the split to get rid of one app. Where does that app go?

Sometimes, you just need to expand one of the two apps up to full screen temporarily in order to do some detailed task. However, when you do that, there is no simple or fast way to recover the previous state of your workspace. When an app is collapsed out of multitasking, it is basically “gone” and you have to reconstruct it from scratch.

As I have already discussed, if the app you’re using isn’t immediately accessible, that can send you back down the path of wondering whether it’s in the Dock or not, then going to the home screen and so on.

The “recents” area in the Dock might be an amelioration but it’s not clear to me what the heuristic is for having an app appear in that space. It doesn’t appear to be a strict “most recently used” algorithm so, again, it’s hard to make a mental model of how that area of the dock can be used consistently to develop a workflow. It’s helpful in an opportunistic sense, but it’s not clearly dependable. I would estimate it contained the app I wanted about 40% of the time and I have since disabled it - again to force all app access down an annoying-but-at-least-consistently-predictable path.

### Mental Models

Ultimately, my big issue with the iOS 11 multitasking model is the demands it places on the user’s mental model. In iOS 11, you have to develop and maintain a mental model of:

- The apps in your Dock
- The apps _not_ in your Dock
- The state of your app pairings
- Which apps were in Slide Over in which spaces

...in order to predict what a behaviour is going to do to your workspace.

Due to the idea of switching spaces and not apps, if your workflow doesn’t have obvious and persistent pairings, I seem to spend an inordinate amount of time tediously rearranging my workspaces to get the apps I want on screen together.

In a system which has pervasive drag and drop, it will often be desirable to arrange things in such a way that the source and target of the drag are both visible at the same time. In that way, it becomes even more important to have access to easy reorganisation of apps in a side-by-side view.

### Conclusion

In summary, there are many things I love about iOS 11 but I find these two fundamental areas of the system to be incredibly frustrating to use in their current form.

We use these areas so much in a typical day. I’m constantly moving between different pairings of apps. All of these enforced pauses in dragging, along with the model of swapping spaces rather than apps, is adding up to making serious work on iOS 11 a very frustrating experience in practice.
