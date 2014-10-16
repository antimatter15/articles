---
title: ShinyTouch/JS
author: admin
date: 2009-08-28 10:17:23
categories:
  - ShinyTouch
  - Touchscreens
tags: 
  - actionscript
  - algorithm
  - canvas
  - complicated
  - elitist
  - flash
  - future
  - hideous
  - html 5
  - javascript
  - js
  - linux
  - port
  - python
  - shiny
  - ugly
  - video
  - webcam
template: article.jade
---

Yay for yet another demo that strives to mix an mash almost everything HTML5 related! ShinyTouch in JS dumps the stuff from a &lt;video&gt; tag with ogg encoded video (well, almost all video from linux is ogg encoded so it's just whatever format i got first from cheese). It gets dumped into &lt;canvas&gt; and getImageData does it's magic.

Interestingly, if you don't use the video and just do data from a raw image, you get upwards of 125fps on V8\. Adding the video, it ceases to work on Chromium (maybe a linux thing? [this](http://code.google.com/p/chromium/issues/detail?id=16225) tells me it's just linux, but you can never be so sure).

    //At this point, run away as the algorithm gets messy and hackish

So the thing just searches from right to left up to down within the quad. When it finds a column of something that fits the rgb range of the finger that is larger than a certain threshold, it checks for a reflection from the point. If it detects a reflection then yay! it throws the data at the perspective warper (based on a python one which is based on a C# one and though it would probably be easier to port from C# to JS making long chains of derivative work is fun). If there wasnt a reflection then it logs that and if that number is larger than some othe rthreshold then it kills the scanning and goes on with it's life. The reflection algorithm just takes the point 5 pixels to the right and assumes that would be a reflection if there was one and a point 15px above and 5px to the left (nasty stuff) and takes the hue value from their RGB values. It takes the absolute value of the difference of the hue values multiplied by 100 (or 200 in the python version) and compares it with a preset configuration variable.

So now that that horrible algorithm which was just whatever came to my little totally untrained mind first. But it works semi-decently, at least for me. But you can hopefully see how nasty it's inner workings are and it inspires people to clean it up. It's quite a bit more readable than the Python version and only 200 lines of JS so it won't be _too_ hard to understand.

But since HTML5 has no Video capture thing for webcams, and my webcam doesn't work with flash so I can't use that canvas&lt;-flash webcam bridge i built, uh, almost 2 years ago. So now you just get to gaze at my finger moving for like 20 seconds!

[http://antimatter15.com/misc/shiny/shinytouch.html](http://antimatter15.com/misc/shiny/shinytouch.html)
