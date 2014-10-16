---
title: ShinyTouch Auto-Calibration
author: admin
date: 2009-07-25 11:01:41
categories:
  - ShinyTouch
  - Touchscreens
tags: 
  - calibrate
  - python
  - screen
  - surface
  - touch
template: article.jade
---

A few days ago I started working on auto calibration for shinytouch. Someone worked it a bit brfire and gave some PyGTK code that did fullscreen correctly but I ended up getting too confused (especially with embedding the video and images and threading delays). So now I started from scratch (or moreover continuing with using pygame) and now it is inherently not full screen. The auto calibration works by setting the contents of he window to be one color and taking a snapshot. After that the color is changes again and the snapshot is once again recorded. After gathering a pair, the software compares them pixel by pixel. It takes multiple trials and takes the average.

Then there is a function that makes cool stuff happen. It goes right to left to search for massive groups of consecutively marked hot pixel change areas. Ir searches for a general trapezoidal shape. And takes the lenghs and heights and positions. And right now, typing on my iPhone I wish the spell corrector was as awesome as the google wave contextual system.
So in the near future, shinytouch will be as simple as launchingthe app and hitting a calibrate button and the computer does the rest. Maybe it might ask you to touch the screen in a special magic box or click on your finger afterwards but overall, zero setup and almost no calibration.
So on another note, shinytouch is now almost a month old idea-wise. In my idea book, the references to it date back to June 28, though it may have originated a few days prior. For shinytouch the beginning window is quite a bit more broad. Anywhere from last year to march. I seem to recall late January experimentation with mirrors.
So now,
With shinytouch being the more promising (more acessible and radical) I have stalled development on mirrortouch. It's quite annoying how fast time passes. There is so much that I really want to do but there is nost not enough time.
