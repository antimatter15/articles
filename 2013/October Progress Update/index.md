---
title: October Progress Update
author: admin
date: 2013-10-31 6:45:14
tags: 
  - 2009
  - aluminium
  - aluminum
  - blue
  - chrome extension
  - chromebook
  - college
  - mac
  - math
  - matlab
  - mittens
  - ocr
  - porting
  - social
  - swt
  - unibody
template: article.jade
---

It's Halloween, and I still haven't posted a monthly blog post and I don't quite feel like retroactively posting something next month. I'm understandably quite starved for free time with my attempts to reconcile sleep with college with social interaction- and from the looks of it, I probably won't be able to publish the blog post that I've been working on for the better half of this month before it the month ends.

For the past five days, I've started using an actual laptop- a late-2013 Macbook Pro Retina 15" (yes, I made it through the better part of two months of college without a laptop more sophisticated than a 2009-era Chromebook). Aside from the obligatory setup process and acclimation to the new operating system, and a mild bout of screen-size-anorexia (which with proper counseling, I've more or less recovered from- the 13" is actually somewhat small, but I still can't quite shake the feeling that 15" is a smidgen too big), the process has been quite painless.

Getting a laptop slightly more capable than the Series 5 Chromebook (not the beefier Celeron model, the original Atom) is a quite long overdue change. I participated in my first hackathon (incidentally also the first time I've really written code since the start of the school year) during the beginning of the month. By the end of that 32-hour stretch, I did yearn for a functional trackpad, larger screen and more performant setup. But my shining knight in Unibody Aluminium armor would not have come until three weeks later. But I don't think the productivity gains would have affected things too much- even with this dinky setup, the prototype scored the second place trophy.

The exact subject of the project was actually discussed briefly in the last progress update, on that long list of projects which I've yet to start. That night, I had actually taken the initiative to do a proper port of some Matlab implementation of the Stroke Width Transform. I hooked it up as a content script which would listen for mouse events over image elements and search for textual regions and draw semitransparent blue boxes where appropriate, and connected it to a node backend which would run tesseract to recognize characters. By the end of it all, I had enough for a pretty impressive demo.

Intermittently for more or less the entire month, I've been trying to improve the project- replacing some of the more hacky bits with more reliable implementations. I've read about some more algorithms, and experimented with different approaches to improve the method. I'm trying to add more stages to the text detection algorithm, such as the ability to segment an image into different lines, and improve the process of splitting lines into characters beyond mere connected components. But the process is rather tedious and with my limited free time, the project remains quite far away from public availability.
