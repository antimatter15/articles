---
title: Python Ports!
author: admin
date: 2009-04-12 10:09:12
categories:
  - MirrorTouch
tags: 
  - linux
  - PIL
  - python
  - rewrite
  - webcam
template: article.jade
---

I'm porting the multitouch concept to python. Why? Because i'm on linux now, mono sucks, and PIL is pretty awesome.

I've set up a mock-rig where there are 2 mirrors on the side angled by erasers with a crappy Creative NX webcam mounted on a textbook over it. It seems like the only practical use of this is for a multitouch-table sort because gravity makes it otherwise pretty hard to calibrate.

So after I rewrite the software I need to try getting it to parse an actual image. Then I need to somehow hook it up to streaming webcam data, and somehow do something else.
