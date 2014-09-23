---
title: Ajax Animator + Wave
author: admin
date: 2009-09-07 9:49:10
tags: 
  - ajax animator
  - animation
  - conspiracy
  - google
  - icantdraw
  - intellectual poverty
  - IP
  - piracy
  - stealing
  - trademarks
  - wave
template: article.jade
---

[![](SadTab-150x150.jpg)](SadTab.jpg) sadly it led to this

So I think that the Ajax Animator Wave thingy is almost done. I think it's really awesome, there's some new stuff in there that may help in collaboration. There is still a bit of dogfooding left (VectorEditor needs to be updated as while the new version of Raphael is being used which eliminates a lot of the hacks being used, the change in path APIs means that lines, polylines and paths all fail). So after a bit of more bug testing, I think it's going to be pretty cool. It will definately be out by the time the 100,000 people join Google Wave (I can't wait!). But I'm not sure if it will be today, next week, or the week after that.

So to show some cool stuff I can do, I'll publish the first time this blog has ever really seen an animation by me. But here's the first animation I've made (It uses the Wave, center and flip plugins which you can access in the script executor, but someone could easily and tediously do this by hand too):

[![Wavey](Wavey.gif "Wavey")](Wavey.gif) Try ignoring the probable trademark infringement.

The cool stuff being used here are first the ability to draw a rectangle, to multi-select, multi-copy, multi-paste and manual repeatition. After that, it's multi-dragged down, and next frame then, the Ax.plugins["center"]() plugin is called which obviously centers all of them (by the Y axis, preserving the X one). Then it goes to the next keyframe and using Ax.plugins["Sine"](100,0.01) (first arg defines multiplier for y axis and latter defines something I forgot, i think multiplier for the current X axis).  Then the same function but with (100,0.02) and then Ax.plugins.flip() to make it look like the wave logo. Do some multi-select and set the color. After that cool stuff, it gets saved as text and opened in OnlyPaths Ajax Animator (which also demos a really cool feature called forwards-compatibility). It gets saved as a GIF and uploaded to my blog after that.
