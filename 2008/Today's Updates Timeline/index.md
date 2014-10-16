---
title: Today's Updates Timeline
author: admin
date: 2008-05-25 9:43:13
categories:
  - Ajax Animator
tags: 

template: article.jade
---

Most of the core functions for creating the timeline has been finished. The biggest change from the current 1.4.7 (Timeline v2) system is the width of each frame. The current lets the browser to snugly create a fit for the text in the frames. the new version uses a very consistent 20px width. The text inside has it's font size changed to fit inside the frame. This makes the frames often harder to see (for big frames) but it gives a more accurate visual representation of the animation, and its easier to click on the frames as they are all uniformly spaced.

The implementation differs from the current implementation a lot (its a rewrite). When a frame is added, it creates a new frame at the end of EVERY layer (which is how things should work...) and when a new layer is created, it contains the same number of frames as all the other frames (the way things should work in the first place). addFrame() is split into two functions addFrame() (the one called by people) and addFrame_core(), the one that is used for more control and overall does less. addFrame() adds a frame to every layer, and addFrame_core() only adds a specified frame to a specified layer. Add Frame Core is a dependency of add frame. A rename_layer() function has been made (there were no names in the current stable implementation)

Another great thing, is that timeline_core.js is the first file to be fully indented properly. Sorta sad, but.... I have to say that this indentation stuff is an aftermath of me learning python in the past few days. So, python definitely is a good thing. If you don't know it, and you suffer from the disease of which is not indenting code, then you should definitely learn it.

A delete layer button has also been added.
