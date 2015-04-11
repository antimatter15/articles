---
title: Auto-Canvas-Fixer/Fixes
author: admin
date: 2008-06-25 8:53:36
categories:
  - Ajax Animator
tags: 

template: article.jade
---

I've created a sort of auto-rescue system. In case something weird happens, and the drawing editor fails to work, there is a quick fix. Just go to the tools toolbar and press 'Reload Canvas', it'll save the state of the current frame, delete all instances of the canvas, reinitialize the editor, and load up the saved state.

Also, i've completely removed the "preload icons" stuff because it's completely useless, and doesn't work.

In other news, i've discovered a flaw in the whole tweening engine, and have no idea how to fix it (if i solve this, i may in turn solve the problem with converting a tween to keyframe). When you try creating a tween, all is well and smooth, until you try tweening a second time, then all things weird start happening.  Items are misplaced, shapes grow uncontrollably, weird things happen. I'm not at my main computer now, so i can't investigate now.

I also have no idea to get values for tweening. Right now, the engine is flexible enough  to easily be modified to support features like rotation/transform tweening and color tweening.

Another big bug (annoying, not depriving of any features) is related with the tween cache. It caches generated tweens, so things speed up as everything's loaded from a cache. Sadly, it doesn't know when to reload the cache. and since the tweening engine is sooo much faster (it's noticably faster), the effect of the cache is probably negligable and may be removed overall.

Also, looking at the YSlow scores (a good F, with a score of ~55 for the  build, and somewhere around 30 for the development version). I may have to do a bit better with the optimization. Knowing i rarely ever test outside localhost (have you ever noticed how fast that is?), its prone to lots of problems (that safari bug... for the longest time). Now, this is more rare, with everything generated by a more elegant compilier and better code. I guess I need to really consider CSS sprites more especially because of the kazillion new tools in the toolbox (i decided not to do this in the beginning because OnlyPaths was expanding so quickly when the toolbox was being built, I felt that there would be lots of new tools before the app got released... i was sorta right)