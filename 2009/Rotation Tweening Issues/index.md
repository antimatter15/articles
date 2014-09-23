---
title: Rotation Tweening Issues
author: admin
date: 2009-09-20 11:49:57
tags: 

template: article.jade
---

This isn't really an issue, but more of a strange problem that is hard to fix, because the intuitive way is no longer expected, and it is almost impossible to make the intuitive way work.

The problem is that if you rotate something like -1 degrees from 0 degrees. The intuitive way to tween would be to go counterclockwise and rotate 1 degree, but mathematically since it converts -1 degrees to 359 degres, it goes a whole clockwise loop.

Now it's hard to fix it because if you made all the numbers negative, turning it 1 degree would result in a massive counterclockwise loop.

The only thing I can think of is to have the editor determine the initial direction and adjust the algorithm accordingly, but some strange things might happen resulting from that.
