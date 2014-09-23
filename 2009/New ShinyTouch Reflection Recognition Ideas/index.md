---
title: New ShinyTouch Reflection Recognition Ideas
author: admin
date: 2009-07-18 4:55:59
tags: 

template: article.jade
---

So the key innovation in ShinyTouch is the using of reflections to determine touches. (Sure there's some  slight innovation with scanning the pixels in a certain way, but that's nothing in comparison to the rest). Right now, it checks colors on only 3 pixels strategically and combines them using some ratios estimated from fresnel's equations. I must be doing some stuff wrong because it's not reliable at all.

So what is reliable and practical? I think maybe just something which recognizes the general characteristics of the reflection (like looking like the actual image) shapewise could work. I dont know.

So i have a little notebook with tons of random sketches on ideas and equations and tiny pseudo-code algorithms to theoretically improve the detection rate.  One is basically analyzing more than teh single pixel it does now, by "measuring" the width of the reflection and matching it up with the image (and in all cases it should be equivalent). The problem is that it's hard to measure, so I have this algorithm which I think may resolve it by comparing the value of  the pixel in question with the known point and the known non-reflection.

But it's nowhere near complete, and ideas are welcome.
