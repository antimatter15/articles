---
title: ShinyTouch is Complicated
author: admin
date: 2009-08-22 7:28:38
categories:
  - ShinyTouch
  - Touchscreens
tags: 

template: article.jade
---

**This is a draft, **and I just feel like publishing it cause I lost my train of thought.

So I totally super insanely over underestimated the complexity of the ShinyTouch project. It's actually probably one of the most complicated projects I've ever attempted. And if all hardware related things are really this complicated, then I really applaud the efforts of all those people who work on this stuff. While ShinyTouch isn't really large code-wise (currently less than 200 lines of Python), it's not a very simple program.

And though the concept can be implemented as a simple thing, you would loose a lot of accuracy. The most basic possible implementation would be to search for a color matching the range for a finger (it does in fact stick out quite a bit) by searching pixel-by pixel from right-to-left (if the camera is mounted to the right of the monitor) and it will stop once it hits the fingertip, which is the first thing of skin that the camera sees since it's mounted at an angle. After that, you would check if the color immediately next to the point and check if it fits in a range. Then if it matches, then you fix the distortion due to perception and send it to a app through something like TUIO.

With that being the most simple thing possible, everything else I've thought of builds on the second part: the reflection detection. This part is what I've discovered to be the most complicated. And the complexity of it isn't totally unexpected. This detection is really all that is truly special about this project. Without it, it's just finger tracking, something that's been used for tons of projects.
