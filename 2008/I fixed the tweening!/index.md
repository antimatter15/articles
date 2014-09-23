---
title: I fixed the tweening!
author: admin
date: 2008-06-26 5:45:44
tags: 

template: article.jade
---

Okay, so there was this HUGE bug that caused tons of problems, i mistaken it for another bug, and spent hours trying to resolve that one. but this was caused by a oneliner function in it. simply, Ax.tweenNumber(). The problem was that the last argument "index", (even according to my *cough* wonderful docuemntation) said, index from _previous_ keyframe. For the index, i simply used the frame that was being tweened. This worked fine because the index was already right, as the previous frame was the first frame. so not having that part of the function didn't matter in that case.

here's a "changelog"
<pre>changelog:

frs0t ps0t:
  return (index/(frame2-frame1))*(value2-value1); //just hope this works!
second edit:
  return value1+(index/(frame2-frame1))*(value2-value1); //just hope this works!
third magical edit:
  return value1+((index-frame1)/(frame2-frame1))*(value2-value1); //just hope this works!

</pre>
