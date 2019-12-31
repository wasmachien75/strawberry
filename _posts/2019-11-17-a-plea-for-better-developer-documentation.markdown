---
layout: post
title:  "Documentation as a feature"
date:   2019-11-17 11:28:00 +0100
tags: [api, documentation]
---

Have you ever wondered what makes the world go around?

Yes, money does its fair share, but at the time of writing, a lot if not most of our daily lives are impacted by digital systems. Importantly, these systems do not work in isolation, but are connected with each other. 

As somebody that works in the broadcasting industry, I get confronted with this on a daily basis. Multiple software programs work with each other to make sure you get to sit in your couch every Sunday to watch the latest Game of Thrones. Here are some of them:

* A content management system (CMS) where all metadata, press information, etc. of the show are stored.
* A media asset management system (MAM) that manages the digital files and contains meta information that helps the schedulers to know at what point they can insert an ad break, for example.
* A rights system that contains legal information. (Broadcast rights can be very complex and fines for not obeying them high.)
* A scheduling system in which playlists are made and uses much of the above information to determine whether a program is ready to broadcast.
* A playout system that does the actual playout.

Now how do all these things connect to each other? It is done through **API's**, which stands for *Application Programming Interface* and very crudely said means that you open your software towards other software. Where human users use a GUI (Graphical User Interface), software uses API's. You can see it more and more creeping into your daily lives. Nowadays, you can listen to Spotify on your fridge. Your car, your TV and even your light bulbs are all connected to the internet. This does not all happen by itself, all these communications are programmed using API's.

There is one big difference between an API and a GUI: **an API can not be self-documenting**. While a GUI can use strategically placed buttons and labels to communicate how it should be used (how many of you have ever opened the documentation of your operating system or word processor?), an API does not have this luxury. You can compare using an API without documentation, to navigating a GUI with your screen turned off. It might work, but it will involve hours of trial and errors and it will not be conducive to your mood. It is therefore imperative that your API is supported with clear, well-written and extensive documentation.

Let me illustrate my point with some examples from some big players:

### Stripe ###

{%include img-link.md img='images/stripe.png' %}

Stripe is a payment processing service that is commonly lauded for their excellent API documentation.

### Microsoft ###

{%include img-link.md img='images/ms_fb.png'%}

Microsoft has a colossal amount of technical documentation for all of their software, programming languages and services. Notice the large range of possibiities to leave feedback. Microsoft recognizes that documentation is never perfect and wants you to tell them how it can be improved.

Interestingly, they have moved all of their documentation to GitHub. This means that everybody can contribute. They even publish style guides that you should adhere to when writing documentation.

{%include img-link.md img='images/ms_sg1.png'%}


{%include img-link.md img='images/ms_sg2.png'%}

### Spotify ###

Spotify doesn't just provide documentation, they straight-up tell you how to create a new front-end app if you're not happy with theirs!

{%include img-link.md img='images/spotify.png'%}

All these companies have one thing in common, which is that that they want you to develop things on their platform. Nowadays, everything is connected to the internet, including your car, your TV and your shower. Amazon literally sells buttons that you can push to automatically order toilet paper if you run out. All systems talk to each other to create an interconnected experience. If your platform does not offer that possibility, you are irrelevant and you will disappear off the map. The easiest way to get developers on your platform is by recognizing developers are inherently lazy, and you should therefore provide accessible documentation that frees them from hours of frustrating trial-and-error.

Here is what I believe makes for good API documentation:

* The basics should be explained in a concise way, so the developer can get quickly started.
* Every single detail should be described. If it's not in the documentation, it might as well not exist.
* Error responses should be explained in as much detail as normal responses.
* It should be written in simple, plain language while still being complete and technically correct.
* No specific knowledge should be presumed.
* Everything should be easily navigable. If I need to look for more than 2 minutes to know how to do a basic operation, your documentation is too complicated.
* Examples, examples, examples.

Conclusion: treat developers as end users. Treat your technical writers as kings. Make sure your **documentation is a feature**, not an afterthought. The Internet of Things revolution has started and you don't want to be left behind.

[stripe]: {{"images/stripe.png" | relative_url}}