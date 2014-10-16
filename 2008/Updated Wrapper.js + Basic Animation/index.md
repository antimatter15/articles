---
title: Updated Wrapper.js + Basic Animation
author: admin
date: 2008-06-17 5:05:23
categories:
  - Ajax Animator
  - OnlyPaths
tags: 

template: article.jade
---

I was working on multi-frame support for the Ajax Animator but it didn't work, so I looked at OnlyPaths again, and it turns out the loading mechanism has changed (no hacks!). Well, yeah... it's great.

Of course, the most important thing is the support for basic (i mean _really_ basic) animation.... So much that it's almost impossible to consider it "animation".

As in basic, there is no keyframe support, and the canvas behaves awkwardly. I guess it'd seem more normal if the canvas emptied itself every time a new frame was not loaded (he he...).

So... yeah. it's pretty interesting.... The animation is stored in a variable named Ax.canvas_storage. it is a javascript object organized by Layer names and then by frames.

so an example of JSON export would be: {"Layer 1":{"1":[{.....},{.....}],"2":[{.....}]}}
The Metadata component to the ALEON (or whatevery you want to call it) is not finalized yet. The ALEON format actually comprises of a blending between the Ax.layers object and the Ax.canvas_storage part.

&nbsp;
