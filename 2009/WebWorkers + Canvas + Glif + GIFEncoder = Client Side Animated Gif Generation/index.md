---
title: WebWorkers + Canvas + Glif + GIFEncoder = Client Side Animated Gif Generation
author: admin
date: 2009-08-18 2:17:00
tags: 
  - fail
template: article.jade
---

With my super awesome PHP-&gt;JS compiler that I made for Freemovie/JS, I ported GIFEncoder (the second of 2 parts of the Ajax Animator which requires a server). So with this I'm really going to be "building on the shoulder's of giants", since all these individual components were made by other people, I'm just mixing them up in a somewhat creative manner.

Though since Glif only supports monochrome, and I'm not aware of any browser supporting canvas.toDataURL("image/gif").

So after this awesome experimentation and my system for merging multiple GIF images into a single animated gif which is yet to be tested for reasons I will detail later.

So I made it and it was cool, and then I added webworkers support, but then I realized the issue isn't that you need webworkers, but that there was an infinite loop. Fixed it and then it works fine except for the fact that it doesn't.

So if you want to rip it's insides apart and try salvaging the disaster, go to [http://antimatter15.com/misc/canvasfail/giftest.htm](http://antimatter15.com/misc/canvasfail/giftest.htm)
