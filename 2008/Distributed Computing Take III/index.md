---
title: Distributed Computing Take III
author: admin
date: 2008-12-31 4:19:10
categories:
  - Javascript Distributed Computing
tags: 
  - algorithm
  - javascript
  - pi
  - wikipedia
template: article.jade
---

I donno why, but i'm revisiting this. I was trawling across Wikipedia one day, and I got to the article about Pi. I tried distributing Pi a while ago, actually, before I did the hashes. But I never ended up implementing it because it didn't seem feasable, as all the algorithims I encountered (or tried porting) required lots of memory, something very hard to distribute for this scenario. But this time, I found [these](http://en.wikipedia.org/wiki/Computing_%C3%8F%C2%80#Digit_extraction_methods). Looking through them, and googling in the process, I found [http://www.omegacoder.com/?p=91](http://www.omegacoder.com/?p=91), and ported it over to Javascript. It was relatively slow compared to the SuperPi implementation in Javascript, but it was easily distributed.

One problem though, is that it gets slower every iteration (to find the net block of digits). Finding .<span style="font-size: small;">141592653 will be roughly 20ms faster than the next 9 digits (it processes in blocks of 9). Not only would it take longer, but it occupied 100% of the CPU, and it would pop up that ever-annoying "This script may make your computer non responsive" window. So I implemented [this](http://www.julienlecomte.net/blog/2007/10/28/) pattern to make it not lock up any browser other than Chrome (and possibly WebKit Nightly).</span>

<span style="font-size: small;">Still, it would take up 100% of the CPU. I ran it overnight and got to digit 17,000.</span>

<span style="font-size: small;">Eventually, it would take about half an hour for a single iteration (at the 20000th digit). With web-based distributed computing, I can't rely much more time than what Google Analytics reports to be 00:02:24 (my Average Time on Site). And that's half an hour with a 3ghz Intel Core 2 Duo (it's dual core, but the script, is single threaded). </span>

<span style="font-size: small;">I then split the function into smaller parts. the main function was split up, and the loops were divided across users. Now, it can scale easily. It uses virtually no visible CPU. and fits well into that 2 minute timeframe.</span>

<span style="font-size: small;">Try it out [here](http://www.antimatter15.com/misc/pisect/test.htm), but don't stay too long, because i only set there to be 500 "jobs".
</span>
