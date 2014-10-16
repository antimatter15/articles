---
title: VectorEditor
author: admin
date: 2008-08-10 8:13:18
categories:
  - Ajax Animator
  - VectorEditor
tags: 
  - experiment
  - raphael
  - SVG
  - vector
template: article.jade
---

I was experiementing with using another framework for Vector editing. So I used the relatively new Raphael framework. I wanted to use dojo.gfx, but I still don't know how to use it without the dojo dependency. Raphael is not as powerful as dojo.gfx, or even OnlyPaths... so, it needs work.

It has many of the features in OnlyPaths, but it keeps the core showTracker() and such functions in the main script, not in the renderer. That allows the system to be simpler, and more easily cross-platform.

I'm not currently using cross-platform event handling. so it only works in Firefox for now, but converting is easy.

http://antimatter15.110mb.com/ajaxanimator/VectorEditor/opr.htm
