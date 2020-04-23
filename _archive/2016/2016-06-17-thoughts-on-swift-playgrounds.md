---
title: "Thoughts on Swift Playgrounds"
date: "2016-06-16"
summary: ""
layout: archive
---

At WWDC 2016 Apple announced Swift Playgrounds for iOS. Swift Playgrounds is an app that is connected to a larger initiative from Apple called "[Everyone Can Code](http://www.apple.com/education/everyone-can-code/)".

Everyone Can Code comprises the Swift Playgrounds app itself, a series of teacher and student guide books on the iBookstore and a suite of curriculum content delivered inside the Swift Playgrounds app.

I've spend the past few days at WWDC getting up to speed on Playgrounds and here is my first-cut at understanding how it all fits together.

### The App

Playgrounds is genuinely a full Swift interpreter built into an iPad app. Although the demo in the Keynote focused on some simple concepts, it's not a toy or limited version of the language.

The app is comprised of two parts: the source view on the left and the live view on the right. The source view is where you type your program and the live view is where you see any output. At the same time, in the right margin of the editor, you can see intermediate results as they are calculated. This has been part of Swift Playgrounds on macOS for some time.

The app supports two kinds of files. The first is the Playground file that you can create using Xcode on a Mac. These files can be transferred to the iPad and run as-is inside Playgrounds on iOS.

The second kind of file is called a Playground Book. This is what you saw in the keynote. It's much richer and supports a nested chapter and page structure that supports navigation as well as basic assessments of success inside each page. The package format is [documented online](https://developer.apple.com/library/prerelease/content/documentation/Xcode/Conceptual/swift_playgrounds_doc_format/index.html).

There are also a range of things that authors can do with each page in a Playground Book to make it easier for beginning programmers to meet success. These include hiding setup code that doesn't need to be seen by the learner, defining "editable regions" to constrain the learner to only type in certain areas and providing hint text in those editable areas.

Another feature of the app is that it freely allows import and export of Playgrounds and Books to other users via AirDrop. In my teaching experience with beginner programming environments, being able to inspect and adapt someone else's code is a very good way to build learners' curiosity and confidence - as well as a bit of competitiveness!

The app also features certain other simplifying tools for entering code. There are colour pickers, image literals and other gestures that make it easier for learners to avoid syntax errors. One simple example is that you can drag out the lower brace of a conditional statement or loop to enclose other statements and everything springs into place when you let go.

The QuickType bar above the keyboard (the area where you get text suggestions) has also been adapted to give code completion suggestions that are sensitive to the context and only let you complete legal code in the language. Authors of Playground Books can also give hints to the suggestions mechanism to constrain it to only show certain symbols or only symbols from certain packages.

It's important - and not at all obvious on first sight - to understand that Playgrounds is not in itself an authoring environment for Playground Books. When a learner works with a Playground Book, their edits to the code in the book are stored as a diff against the original content in the book. The original content is never modified, but the diffs do get transferred with the book when it's sent to other users. The reason it's done this way is that it facilitates resetting a page in the book to its original state if the user needs to. You can also reset the entire book.

The other thing that is not entirely obvious is that Playgrounds has _full access to the entire iOS API_. This means that there is effectively no limit on the complexity of Playground that you can build. You can use APIs like Core Location, WebKit, MapKit, Core Motion, Networking and Core Bluetooth. One of the demos given in the session on Playgrounds was of Playground Swift code controlling a Sphero robot over Bluetooth. I already did the standard daft Browser-in-five-lines-of-code trick that we used to do on the Mac.

### The Swift Language

A broader question than "is the app any good?" is whether or not the Swift language itself is any good for Computer Science education. I have in my career taught children to program in Visual Basic, Ruby and Most recently Python.

As a Computer Science teacher, I need to know that Swift is a good language for learning to program with. One simplistic approach to promoting Swift in CS is simply to make the argument that kids love smartphones and apps are written in Swift therefore CS education should happen in Swift. I get the thinking behind that but it feels as zeitgeisty as the other moves that teachers make to co-opt anything that kids like and turn it into "education". Remember Second Life? And .... dare I say it .... Minecraft In the fullness of time?

I prefer to ask which specific language features in Swift make the language a good choice for learners. I challenged Apple staff this week to make that case and I came away with some good points. One of the things I particularly liked was that Swift leans toward explicitness rather than implicit or inferred behaviours.

Swift also has API design guidelines focused on expressiveness and understandability rather than terseness. It's also a relatively new language. This certainly has its drawbacks in that the language has changed substantially over the last two major revisions but there is a consistency and clarity to its approach that is sometimes missing from languages like Python.

### What's Not to Like?

Swift Playgrounds is a very new app on iOS. Although it's fairly complete, there are a few things I feel that it still needs.

Firstly, I mentioned that there are ways to get the Playgrounds app to render your code by omitting and hinting certain areas. There's currently no way to get that rendered view out of the app. This is important for teaching in two ways: firstly, it would allow students to submit work to a teacher through iTunes U. The second reason is that a teacher authoring a solution would be able to give a printout of a completed (rendered) version to a pupil who needed it for whatever reason - perhaps a pupil with learning difficulties for whom copying in a provided solution would represent a good achievement. Giving these pupils the full unrendered source would be overwhelming.

The bigger issue right now is that the authoring environment for Playground Books is Xcode on macOS. I'll invite you to use the fingers of maybe both hands to count the number of teachers in your area who (a) even have a Mac and (b) are _au fait_ with Xcode.

I have seen many times that any time the phrase "you use a Mac for that" is a total and complete show-stopper in education. This was true for iTunes U before Course Manager came to iOS and it's still true for iBooks Author.

I think there might, in time, be ways to create Playgrounds and Playground Books on iOS but it will be neither easy nor convenient for some time to come. This isn't an unexpected problem but it is still a problem.

Overall, though, it's hard to find anything seriously bad to say about Swift Playgrounds except that it's an early, immature product right now. Despite that, it already has serious power under the hood and some impressive curriculum content. Can't wait to see where this goes.
