---
title: "Teaching Programming on iOS"
date: "2012-08-17"
---

I have been working for some time on a plan to move my programming classes off Macs and onto iPads. It's finally happening this year. A few people have asked me to write this up, so here goes.

As everyone knows, there are no fully-fledged software development environments for iOS. The closest is a game programming environment called Codea which, while good, doesn't easily map to the kinds of things we currently teach in exam-level Computing courses.

A few years ago, I used to teach using RealBasic on OS X. RealBasic is a fairly standard clone of VisualBasic, the language and IDE that (I guess) most Computing courses are taught with. I hated it. I hated it because the evident link between the code you wrote and the way it executes is quite obscure. I spent as much time explaining where you should type in the code as I did explaining the actual code itself.

Two years ago, I decided to change things. I switched to teaching in Ruby and I switched to using a text editor (TextWrangler) and Terminal. The simplicity is glorious! A simple link between code and result, and no magic glue in-between. I fully appreciate that libraries, frameworks and runtime support are all essential to scale software development up to real-world dimensions but that's not the game I'm playing.

### Enter iPad

One of the astonishing results of our iPad 1:1 deployment has been the dramatic decline in the use of the Mac. Within less than two years, I am the only teacher still using the Mac on a regular basis. This was never part of the plan and I didn't expect that it would happen so soon. I thought it might happen eventually - perhaps in 3-4 years, certainly after one more refresh of our Mac setup.

Today, it quite seriously looks like we won't buy more than a handful of Macs again. We’re not cutting our teaching to fit what the iPad can do either - we have never done more with ICT, with better outcomes and deeper learning than we are doing now with iPads in everyone's hands.

### Taking Programming Mobile (and Virtual)

So, how do we take Ruby programming mobile? Turns out, it's not so hard (assuming you understand AWS cloud computing infrastructure, IP addressing, SSH configuration and Linux sysadmin, naturally).

The basic idea is that we are going to set up an Amazon EC2 instance, SSH into it and edit and execute our code over there. There are several really nice SSH clients for iOS. My personal favourite is Prompt by Panic, but the idea is the same regardless of the client.

### AWS Basics

In case you're not all that familiar with virtualised cloud computing, here's a basic run-down.

Amazon EC2 allows you to spin up a virtual Linux or Windows sever running on Amazon's computing infrastructure. You can start and stop an instance as you need it, and you only pay for the time the instance is running. Instances can run in one of several geographic areas and prices vary slightly from region to region. For my deployment, I used the EU (Ireland) region because we are going to be working interactively and want the lowest latency possible.

The per-hour prices vary by the capability of the virtual machine but, for our purposes, we don't need massive power. The per-hour costs for the smaller instances are incredibly low. An on-demand "Micro" instance costs $0.02/hour. Two cents per hour. So you fire up one of these EC2 instances in August and shut it down the next June, you're going to pay about £80. If you only run it during the school day, it's about £20 per year.

Given that we're deploying iPad anyway for all the other parts of the school, you can see how provisioning a lab just for a programming class isn't an easy conversation to have. By my calculations, my subject now costs the school £10.80 per pupil per year to run. If I had to keep buying Macs just for Computing, the per-head cost would be over £160/year.

### Benefits

I'm a huge fan of strategic outsourcing. We are rapidly moving towards a situation at Cedars where we will have essentially no infrastructure in the school except for WiFi (and possibly [not even that](/blog/2012/7/20/the-2012-ade-institute.html)). This is deliberate: I am the only technician, systems administrator and network manager in the school. I simply don't have time to deal with deploying and looking after servers on the premises. Neither do I want to. I would much rather spend my expensive and valuable time working on things educational rather than things technical.

In order to run my class with computing resources on-site, I would have to manage a suite of laptops or desktop computers, with some kind of file server and directory infrastructure. Alternatively, I can pay Amazon a penny an hour and I don't have to care about hardware at all.

The benefits go beyond the infrastructure and finance, though. It's never been possible for me to set actual programming homework before because few families have development tools installed on their home computers. Now, though, because I know the device that's gone home and I know that the server environment is available from anywhere, I can start to set programming exercises to do at home.

### Workflow

The basic programming workflow for the student looks like this: we use Prompt to connect to the server over SSH and execute the Ruby code over there. Up to now, I've been having the students edit their code using the nano text editor over a second SSH connection as it's relatively approachable for new users of command-line editors.

After some more investigation and help from Twitter pals, I realised that both Textastic (which we've used before for teaching HTML editing) and Diet Coda can edit a file and save it back to an SFTP server relatively transparently. There are advantages and disadvantages to both: Textastic is a far better Ruby editor, but Diet Coda has both editor and terminal integrated in the one app. I'm probably going to go with a combination of Textastic and Prompt for now, since we've already deployed both of those apps.

I think that programming is going to be that one special case where a hardware keyboard on an iPad is really important for two reasons: firstly, several common programming symbols are only accessible through the 'mathematical' keyboard on iOS. To type a "<" symbol, for example, you have to hit the '.?123' key, then the '#+=' key and then type the symbol. Prompt allows four customisable soft keys above the keyboard but there are often more required in programming. Textastic does have a special 'symbols bar' that allows quick access to many symbols, so it will be interesting to see if clever UI design can mitigate this problem.

The second reason for using an external keyboard is to recover even more screen space on the device. Programming using the software keyboard is possible in a pinch - great for doing something quick on the go - but you want as much screen space as possible for code.

### The Evolution of iOS

I'll let you know how this goes, but I think this is a fascinating step in the evolution of the use of iOS in education. We're starting to solve some of the harder parts of the curriculum. Computer programming was one thing that people said the iPad would "never" be suitable for. Certainly, a lab of 27" iMacs would be preferable but the simple truth is that Computing Studies is not a sufficiently important part of the curriculum that the requirements of that subject can dominate the whole-school approach to IT. It's iOS's world; we just live in it.

In a sense, yes, I'm cheating in that I'm not actually programming _on_ the iPad itself but so what? The entire point of mobile devices is that a good proportion of their power comes from being always connected to the Internet. You wouldn't say that you can't search the web with an iPad just because you can't store and search Google's index database on the device.

The idea of not owning infrastructure is really interesting and important to me. I want to stay as agile as possible with our technology and buying only what I need when I need it is an important part of this.
