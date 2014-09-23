---
title: VectorEditor on Wave
author: admin
date: 2009-08-12 7:00:28
tags: 
  - google
  - google wave
  - ie
  - internet exploder
  - microsoft
  - pygowave
  - SVG
  - svg-edit
  - vectoreditor
  - wave
template: article.jade
---

So I don't actually have wave yet, but for all 2 of you (likely less) who have used [pygowave](http://pygowave.p2k-network.org/waves/), an [open source ](http://code.google.com/p/pygowave-server/)third party implementation of the [wave protocol](http://www.waveprotocol.org/). So there was how I developed it, I read through the APIs and tested on pygowave. So what does VectorEditor do that [svg-edit](http://code.google.com/p/svg-edit/) and... erm... [svg-edit](http://www.hokstad.com/static/wave/gadgets.html) don't do?

First, VectorEditor for wave is _really really_ real time. Waaay more real time than svg-edit (not really). But VectorEdit (VectorWave might be a nice name.. I'm going to try using that name from now on in this post) transmits the data such as even **while** the shape is still being drawn, rotated, or moved (rotation needs work). Another nice feature is that the transitions are animated so things are even more seamless.

Another important feature is shape locking. So when someone selects a shape, it gets locked and can't be edited by anyone else. If anyone tries, an alert box appears saying "Shape shape:5sdfwef98dfe3ssdf is locked by user antimatter15@pygowave.p2k-network.org". svg-edit (the latter) doesn't support moving things after they're created so it doesn't really matter then, and I'm quite certain the former doesn't do any type of locking.

And lets not forget the likely most important, yet totally untested feature that seperates VectorEditor from the rest: IE support, which is inherent since it uses Raphael for rendering, but [it may not be necessary](http://www.theregister.co.uk/2009/06/03/google_svg_internet_explorer/) since google may be making some shim-type system of hacking svg awesomeness onto IE and making the whole VectorEditor project useless.

So if you want to try it out, go to pygowave, sign up, create a wave and add the
