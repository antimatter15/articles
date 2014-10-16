---
title: Ajax Animator + Vector Editor
author: admin
date: 2009-07-24 11:00:33
categories:
  - Ajax Animator
tags: 
  - new
  - port
  - vectoreditor
template: article.jade
---

So yesterday, I worked a little on making a VectorEditor based Ajax Animator. It actually took suprisingly little work. The mostly modular and abstracted design of the Ajax Animator means that only a few files need to be changed. Mainly those in the js/drawing directory. Though there was a bunch of references to Ax.canvas.renderer.removeAll() which needed to be changed.

Another cool feature in that version is the ability to have layers show up concurrently. So you can see things while drawing just as they would be in export.

However, it's not ready, it's very very buggy, Lines and Paths aren't tweenable yet, and it's missing all those nice features of OnlyPaths that VectorEditor inherently lacks.

But the one really nice feature I think is the multi select. You can easily select a group of things which comprise some sort of shape, and move it all across.
