---
title: 0.21 Bugfixes
author: admin
date: 2008-08-04 1:23:04
categories:
  - Ajax Animator
tags: 
  - bugfix
  - javafx
  - tween
  - update
template: article.jade
---

I fixed this bug where if you drew a square, went to a blank frame, moved it, and then went to a blank frame (do nothing), and go back to a tween (between first and last frame), the tween engine would crash, and the animation would be destroyed. Fixed by wrapping SVGRenderer's remove function in a try..catch loop.

I also split diff_core into diff_attr which allows you to diff only a single attribute at a time. I also added a diff_list function which would make it easier to implement an export format to a tweening engine like that of JavaFX and Silverlight.

On that note, I added fake support for JavaFX. so you now see the toolbar icon, and I added the script for javafx though there's nothing in it.
