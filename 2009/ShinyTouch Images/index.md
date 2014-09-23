---
title: ShinyTouch Images
author: admin
date: 2009-08-01 11:15:05
tags: 
  - app
  - calibration
  - elitist
  - images
  - nuigroup
  - paranoia
  - python
  - screenshot
  - webcam
template: article.jade
---

This is the app running, notice that it's not yet been calibrated yet.

![](screenshot_012_YR3t87.png)

Here is the auto-calibration process, it alternates between black and white
![](screenshot_011_wZ7Pn1.png)

This is part of Auto-Calibration.
![](screenshot_005_6MQO0S.png)

This is some stuff from the command line:
![](screenshot_007_2rbhHD.png)

This is just hovering over the screen, notice it's not touching, and the algorithm can distinctly recognize the lack of a touch because the reflection is seperated from the finger by a significant gap. (Compare the top red bar).
![](screenshot_006_nV186Y.png)

This is a actual touch, you can see that the red bar is far larger, and it's very distinctly a touch event.
![](screenshot_008_117vhL.png)

There's a draw tool and, here is a primitive drawing of a smiley. The dots come from an issue with PIL/OpenCV or something that makes the image all chopped up and sends the point to an arbitary point on the screen.
![](http://antimatter15.com/misc/img/purty2009-07-21T19:23:30.080675.png)

This is the magical sensor the whole thing is powered by: An unmodified Playstation 3 Eye on a tissue box with a pink Office Depot eraser on the back (because the camera is made tilted and the script can't handle those tilts very well)
![](screenshot_013_5jru8J.png)

It's not too insanely slow either. This is 31 frames per second coming from a pure python app, all from a scripting language. It is nowhere as fast as the normal fast native apps.
