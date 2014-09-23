---
title: Support for multiple layers!
author: admin
date: 2008-06-28 4:47:06
tags: 

template: article.jade
---

you can now have multiple layers!!!!!

Layers basically let you have multiple things going on in an organized fashon. so you can have a layer named "background", and another named "middleground" and one named "foreground" where you make the background, and never see it again until you preview while working on the other ones. 

One major issue, is that there really is no positioning associated with layers, so you can't D&amp;D (drag n drop) reorder layers so the foreground is in front of the background things.

All i had to do to support layers was to add these 3 lines of code to Ax.addLayer()

<font face="Courier New">if(!Ax.canvas_storage[layername]){
    Ax.canvas_storage[layername] = {"1":[]};//create a canvas storage slot with first frame set to blank
  }
  </font>
