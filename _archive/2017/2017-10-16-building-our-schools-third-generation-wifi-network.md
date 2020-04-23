---
title: "Building our School's Third-Generation WiFi Network"
date: "2017-10-16"
---

I recently completed our school’s third wifi deployment which has been by far our best and most comprehensive network to date. I thought I would write up a bit about it here.

To understand a bit about our deployment, you need to know that our school building is an old stone building from the second half of the 19th century. It was very definitely not built as a school and the original designers did not take a lot of care to make WiFi deployments easy!

We cabled most of the building in the mid-2000s to accommodate wired networking for, at the time, desktop computers. Since we moved to iPad in 2010, a lot of that network has lain dark and unused.

Our first WiFi network was installed in 2008. At that time, we were using Apple Airport Extremes. The school at the time was quite small numerically - we had just moved up from a much smaller building - and we were recruiting new pupils all the time.

The AirPort Extreme network worked fine for the internet capacity and number of machines we had at the time. I think we probably had about 20 machines on the WiFi and the entire school ran off a 5 megabit internet connection.

At the time, we also had a fairly basic Netgear smart switch connecting everything in the networking cupboard. This switch was the unit that wouldn’t die and served us well right through to our new deployment.

In 2010, we went one-to-one iPad and, remarkably, the combination of Airport Extremes and a 5 megabit internet connection coped well for the first few years of the deployment. Again, you have to remember that people’s expectations of the internet were quite low at this time. Many people didn’t have very good or reliable wifi at home and their broadband speeds were quite low as well. Additionally, we were still learning how to be a one-to-one school and few teachers were prepared to depend on the internet connection for the critical work of the school. All of that is different now.

In 2012, we moved to Aerohive. Due to various constraints, we basically replaced the Airport equipment with the Aerohive equipment unit-for-unit. This left us with a network of 9 Aerohive AP330s which, again for the time, was enough to see us through.

As the school grew and grew and more rooms in the building were brought into use, our network started to strain a bit at the edges. We have 15 teaching rooms in the school and with only 9 access points and thick walls to penetrate, things got to the point where I had tweaked and tweaked every setting I could find on the Aerohive network but I wasn’t able to wring any more performance or coverage out of that set of equipment.

On top of that, we were now running iPad hardware that was 802.11ac compatible. Our three iPad deployments to date have been: original iPad, 4th generation iPad and, currently, a split 9.7 iPad Pro/4th generation iPad mini deployment. Finally, we are on student equipment that supports 802.11ac. It was time to do something.

## Ubiquitous Ubiquiti

My first idea was to buy some additional used Aerohive equipment to expand the network just a bit. Unfortunately, that was a non-starter as Aerohive equipment is tied to a server-side license and Aerohive won’t sell you a license for used equipment.

So we started to look around. It seemed to me that we really needed to redesign the whole network since we hadn’t really touched the core switch gear since the mid-2000s and my sense was that, after more than ten years continuous operation, our switch might fail at any time and leave us in a pretty bad situation.

To do the whole network at the quality level I wanted, the main aim was to simply get more radio hardware into the building - one access point per classroom was my goal. That would let us maintain the coverage but reduce the power levels on the access points so that every class was provided with a good signal for that room and iPads would be strongly encouraged to connect to the AP in the room they were in.

Previously, because of our need to penetrate thick walls, we were running several access points at maximum power and this was causing problems with devices not roaming correctly to the closest AP. This caused a lot of trouble with people moving around the school with iPads open and getting stuck on various high-powered access points - which sometimes were quite far away from where the students were.

So I put together a proposal to basically replace everything with modern, supported and managed networking equipment. Realistically, for our budget and the scale we wanted to operate at now, Ubiquiti’s Unifi range was more or less the only game in town.

The final proposal was as follows:

- One Ubiquiti Security Gateway to act as our border router (we still had one AirPort Extreme doing this job for us!)
- One US-24-250W switch to connect the ground floor together
- Two US-8-150W switches to connect the first and second floors together
- 20 Unifi AP-AC-PRO access points

20 APs would give us:

- One AP in each working room in the school
- Two APs in the lunch room and our biggest classroom which is often used by many students simultaneously
- An AP in the hallway on the first two floors
- One spare

The proposal was approved quite quickly and it was on to designing the roll-out.

## Deploying the Controller

The Ubiquiti licensing model is both more straightforward and far cheaper than most (all?) “enterprise” wifi networking systems: you buy the kit and download the controller from their website and you’re off to the races.

I decided, as is my wont, to deploy the controller on an Amazon EC2 Linux machine running Ubuntu server. This is how we do our MDM server too and it works well for us.

Well before the equipment was even ordered, I had set up the controller and had designed the shape of the network so that, when the kit arrived, it was a matter of going through what Ubiquiti calls “adoption” for each piece of kit and it would all be up and running.

The big difference between running the controller on your LAN and running it in the cloud is that you need to do what’s called “\[Layer 3 Adoption\]” - that is, you need to tell the equipment where its controller is. If you’re on the same LAN, it will be automatically discovered.

## Rolling Out

The first job was to replace the last AirPort Extreme with the Security Gateway. The USG is basically a two-port router that sits on the edge of your network. I configured ours so that one port would be the new network and the second port would emulate the old network. That way, I could drop in the USG between the existing network and the internet and nobody would notice anything.

That step actually worked beautifully and I was able to start setting up the new network in parallel with running the old network. I next installed the 24-port switch and hooked it up to the USG - our new network was off to the races.

My next steps were to unpack and set up the other two switches and all the access points. I wanted to do this at my desk because we were going to install some of these APs in reasonably inaccessible places and if anything was going to go wrong with them, I wanted to know before we got the ladders out.

I started working through the APs, connecting them to the switch, adopting them into the controller and giving them friendly names and then, crucially, physically labelling them with the same name that they have in the controller.

I can’t emphasise this last point enough: **80% of effective systems administration is labelling things correctly and methodically**.

Between other things, this process took me a couple of days. The equipment had been delivered on Monday lunchtime and by Wednesday evening I was ready to start installing equipment. We worked all day on Thursday mounting APs on the walls and cutting new cables to connect everything up. Some rooms had dark cable in the walls so it was a simple job to cut a drop cable and wire up the AP.

Other rooms had existing unmanaged switchgear in so we mounted the new equipment in parallel with the old stuff and waited until we were about to switch over. By about 5pm on Thursday we had all the APs installed and the switches on each floor were ready to go.

On Thursday evening I went back into school with the intention of trying to hook up a few APs and test the signal. In the end, I decided that I was so close to being done that I might as well complete the job. In about 4 hours of pulling cable and re-wiring, I had the entire new network up and running. It felt great to pull out all that old gear and eliminate all the little unmanaged switches we had accumulated over the course of ten years of piecemeal network expansion.

On the Friday, we ran for the first day on our new network and, as best as I could tell, it was a rousing success. Many of the worst-served classrooms reported much more stable, reliable and fast connections. The better-served classrooms simply didn’t notice anything.

WiFi is one of these “hygiene” features in school - there’s no great kudos for having it work perfectly all the time but there is a ton of heartache when it doesn’t work well for everything. Ideally, I want nobody to notice the WiFi at all. If people are talking about it, there’s a problem.

## iPad Configuration

Moving from Aerohive to Ubiquiti was not without a couple of interesting issues. We had been using Aerohive’s Private Pre-shared Key feature to give every student a unique password to the network. This is a flagship Aerohive feature and it has some significant advantages but I found that, in practice, it had a number of downsides too.

We had arranged things so that each student password was only good for one device but, since the students knew their own password, they could easily use it on another wifi device that they owned and brought to school - usually their smartphone but I did see the occasional Kindle appearing too. What this resulted in was a kind of race condition where the first device that came in the door in the morning would “use up” the slot for that student and their school iPad wouldn’t be able to join the network.

Ubiquiti doesn’t have an equivalent feature - except by using RADIUS, which I didn’t really want to set up - so before I rolled out the new network, I sent a configuration profile to all the student iPads with a new WiFi payload that contained the SSID and password for the new network.

This also worked very well. As soon as I brought up the new WiFi network, student devices started to join the new network without my ever touching them.

On the first day of operation, I spent time watching the Ubiquiti dashboard alongside the school timetable. What I was looking for was to see that iPads were roaming correctly to the AP in the class that the student was actually sitting in. For the most part that worked very well and I could usually find a student iPad by looking at the client list for the classroom that the timetable said they would be in.

I did some work to manually set channels and power levels for all the access points. I set the 2.4GHz radios to “low” power (9 dBm) and the 5GHz radios to “medium” (17 dBm) everywhere. I’m still tweaking some channels to make sure that APs are not interfering with each other. Ubiquiti’s auto channel selection system basically chooses the best channel at startup and stays there (other systems perform occasional background scanning and switch), so it does rather lead you to hand-tweaking just to be sure.

So that’s the story of our new network and how we built it in a week. I’ve been very pleased by both the price and performance of the Ubiquiti equipment. The licensing model is the kind that I like (i.e. not very “enterprisey”) and I didn’t even mention this but the Unifi iOS app is one of the best native apps I’ve ever seen for wifi management.
