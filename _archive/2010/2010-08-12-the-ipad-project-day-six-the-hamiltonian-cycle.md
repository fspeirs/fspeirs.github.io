---
title: "The iPad Project: Day Six - The Hamiltonian Cycle"
date: "2010-08-12"
---

It's time to talk about app distribution. Recall that we have one computer, one Mac OS X user account and one iTunes library in each primary classroom. There are four classrooms and a 'master' computer to use up our total of five authorised computers.

These machines all share one iTunes account.

Requirements:

- That any teacher can buy an app for their class without going to the IT Department (er, me) to get it done.
- That any app purchased will be available to all the primary classes without manual intervention from the IT Department (er, again, me).

The setup:

- Five computers (A B C D and E) authorised for the account.
- Turn on Home Sharing on them all.
- A is the "master" library.
- B, C, D and E are set to automatically copy content from A.
- A is set to automatically copy content from B, C, D and E.
- B, C, D and E do not look at each other's home shares.

Buy an app on A:

- B, C, D and E will see the app and copy it.
- Happy days.

Buy an app on B:

- A will see the app and copy it.

At this point, ideally, machine A would inform C, D and E that it has a new app, they'll copy it and everyone is consistent. Not so.

What actually happens is that the "I have new content from the iTunes Store" notification is only broadcast from the machine that actually transacted with the store. So A gets notified but then A doesn't tell C, D and E.

Turns out that the other iTunes machines will only automatically check A's Home Share when iTunes is relaunched.

I guess this was done to avoid a flood of "new app!" notifications rippling through the network but, since one Home Share network can only contain at most 5 machines, that problem is self limiting.

### Solutions

The solution I came up with was to have every machine in the Home Share group look at the libraries of every other machine. A fully-connected graph, if you like.

This now lets teachers in any class buy an app and have it automatically appear in the libraries of all the other classes.

### The Secondary Department

It's not going to be this easy in Secondary because of the requirement that every pupil sync their iPad to their own user account.

For secondary, it will have to be the case that "IT" has to purchase an app on the "master" computer and everyone's iTunes is set up to automatically pull from that machine over Home Sharing.
