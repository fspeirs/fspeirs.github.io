---
title: "Teaching Programming with iOS and Amazon EC2"
date: "2013-04-04"
summary: "Another refinement on teaching programming on iOS. Swift Playgrounds would eventually make this a lot easier."
layout: archive
---

I just shut down the Amazon EC2 instance we've been using all school year, so I thought it was worth reflecting on. Last August, I [wrote about my new approach to teaching Ruby programming on our iPads](/blog/2012/8/17/teaching-programming-on-ios.html).

How did it work? In a word: perfectly.

### The Server Side

Back in August, I set up an Amazon EC2 instance. I used the standard Amazon Linux AMI, and launched it in a Micro instance. For neatness, I allocated an Elastic IP Address to the instance and created a sensible DNS name for it.

The next step was to set up user accounts for each pupil. I did this manually because I could, but it's easily automatable if you needed to. Our iOS SSH client, Prompt, supports using SSH keypairs for authentication but distributing the private keys is a little fiddly so I reconfigured SSH on the server to allow password authentication.

Responsiveness of the remote server wasn't an issue at all. We used the EU West (Ireland) region for our Amazon EC2 instance so it wasn't far away from us and the interactive response was just fine. I'm not sure it would have been ideal to actually edit code in, but it was perfectly fine for running programs.

We ran into no problems with with the EC2 server at all. I set it up, it ran for over 5,000 hours of operation without a hitch and I turned it off today. All-in, it cost me £65 to run this server for the past academic year. I didn't do anything to limit the time the server ran - it was on 24x7 for the whole year. If I had automated shutting it down at, say, 10pm and relaunching it at 9am, I could have cut the cost to about £35 for the year but it's almost not worth my time to bother.

### The Client Side

In my last piece, I was debating the exact combination of software to use. In the end, we settled on using [Prompt](http://panic.com/prompt/) for our SSH client and [Textastic](http://www.textasticapp.com) to edit the code.

Textastic has a really nice feature whereby, if a file was initially downloaded from a remote server, Textastic can send the file back where it came from with one tap. This really helped the overall workflow.

The idea of switching between two apps to edit and run code didn't seem to have much impact on pupils. With the multitasking gestures in use, the switch was easy enough. The biggest complaint was that, on our iPad 1s, resuming the switched-to app was slower than we would have liked. This problem will go away after our refresh.

Occasionally, Prompt wouldn't maintain the connection to the server while the pupils were editing code in Textastic. I haven't yet figured out if that's just a bug or if there's some server-side timeout happening. It wasn't a frequent enough occurrence to warrant a lot of debugging.

### The Hardware

This class was the first time we had deployed Bluetooth keyboards for use with the iPad. When you're programming, you're always reaching for those weird symbols in the second and third keyboards on the iPad. Textastic does a good job of trying to help you by creating a row of five-way buttons across the top of the standard keyboard that allow quick access to a large number of symbols. The downside to this is that you lose even more screen space for seeing your code.

For these classes, I bought a number of [these Bluetooth keyboards](http://www.amazon.co.uk/Bluetooth-Wireless-Keyboard-Ericsson-Blackberry/dp/B004J4B0MA). They cost £9.16 on Amazon and they held up perfectly well for the year. They're not quite as delightful to type on as an Apple Bluetooth keyboard but they do the job just fine and none of them broke.

### The Workflow

Once students complete an assignment, they have to turn in a report with some text, their source code and evidence of systematic testing of their code. We went through a few iterations of the exact workflow for this but, in the end, we settled on copying and pasting the code from Textastic and the testing runs from Prompt into Pages and presenting them in a monospaced font along with the rest of the report. The only downside to this workflow is that you lose the syntax colouring from Textastic.

This document was then emailed to me as a PDF where I could mark it digitally using PDF Expert on my iPad and return it to the students via email and archive my copy.

### The Future

I'll definitely continue doing this. Given the success of this project, it's almost inconceivable that we could justify provisioning a whole computer lab for just one subject.

On a wider note, I think this milestone is emblematic of the increasing maturity of iOS. In 2010, computer programming was one of the cardinal subjects that iPad sceptics insisted it would "never" be possible to teach using an iPad. Well, guess what? Add another item to the pile of things that people said would "never" be possible in computing.

Never's a long time.
