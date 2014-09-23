---
title: New ShinyTouch Algorithms
author: admin
date: 2009-07-21 6:18:33
tags: 
  - complicated
  - config
  - configuration
  - elitist
  - hsv
template: article.jade
---

The algorithms are nearing completion. They now function most of the time and are fairly situation-agnostic and mostly zero-config.

A cool new thing it does now is using the HSV color space rather than the RGB one and comparing the hue values. It turns out that this creates the most noticable difference between colors and it can easily tell different colors and shapes apart.

There is also a new shape-detection system, because all previous ones checked colors. This works by getting a sample of the finger color and the background color and comparing the closeness of surrounding pixels to each one. It ends when it finds a pixel closer to the bg than the finger. This one is truly zero config.

Another one checks the similarities in hue of the alleged reflection color and the known bg color. If it's not similar enough, then it is recognized as a touch. It does use some configuration, but it shouldn't vary much from situation-to-situation to require serious configuration.

There is also a new failure, which is generating a supposed ideal sum ratio to detect things (which is how the newly old one worked backwards). Though it spawned a new version that uses HSV instead, and it works pretty well.

Also, almost all the functions now create bar-graph visualizations. Very futuristic and augmented-reality style.
