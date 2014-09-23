---
title: Timeline + New OnlyPaths
author: admin
date: 2008-06-15 12:34:15
tags: 

template: article.jade
---

I've updated the OnlyPaths version (to the latest one) so there may be some compatability issues, but it is still overall better (more stable, btw). A very awesome new feature: the timeline. Well, the timeline is already _there_ but I added a very important part: the selection model. Its brilliant becasue now, i dont have to manage 3*2=6 states (blank, keyframe, tween and selected for all), but rather, only 3+1 states (blank, keyframe, tween, and a semitransparent selection mask) and a selection cursor. It makes the code much more elegant, as you have one little semitransparent cursor that masks the selected frame. Its also faster as you don't have to unselect the past frame, look up the type of the old one, set that, look up the current one, set the new one, etc.
