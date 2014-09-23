---
title: Ajax Animator iPad Support
author: admin
date: 2010-04-11 8:51:14
tags: 
  - ajax animator
  - apple
  - clarke
  - experiment
  - ios
  - ipad
  - magical
  - mobile safari
  - vectoreditor
template: article.jade
---

Today I went to the magical Apple Store and tried out the iPad for the first time. I really have to say that it's quite magical, though it doesn't fulfill the criterion for [Arthur C. Clarke's Third Law](http://en.wikipedia.org/wiki/Clarke) despite what [Jonathan Ive](http://www.apple.com/ipad/#video) says. Though I really haven't tried any large area multitouch interface before (sadly), and I would expect it to be a somewhat similar if not exact replica of the experience. Keynote and Numbers were pretty neat (I suck at typing on the iPad in any orientation, so I don't like Pages). That's enough to show that iPad is not just a content consumption tool as the iPod and iPhone primarily are, but also content creation.

Anyway, in a few minutes I just swapped the mousedown, mousemove, mouseup events with touchstart, touchmove, touchend events respectively in the core of VectorEditor, while adding a new MobileSafari detection script (var mobilesafari = /AppleWebKit.*Mobile/.test(navigator.userAgent);) and in a quite analogous "magical" way, V[ectorEditor works in iPhone/iPod Touch](http://code.google.com/p/jsvectoreditor/source/detail?r=202) and theoretically iPad, Just dragging the vectoreditor files over to the Ajax Animator folder and recompiling should bring iPad support to Ajax Animator with virtually no work.

I haven't tested it. Downloading XCode 3.2.2 right now so hopefully I can test it soon. Stupid how it's what? 2.31 gigabytes?!

And possibly, I could use PhoneGap to hack together a App Store app which does the same thing (and maybe charge for it, which might be a bit cruel as this application is open source and works equivalently online - but I guess that's okay for those people who don't read my blog &gt;:) ). Maybe get enough to buy an iPad :P

Anyway, though I'm pretty late to this and my opinion probably doesn't matter at all, here's a mini iPad review: It's really really cool, feels sort of heavy, really expensive, hard to type on in any orientation (interestingly it has that little linke on the f and j keys with the keyboard which feels useless since I always thought the point of that was so you can tactile-ily or haptically or tactically or whatever the right word is, find the home row, but since there's no physical dimension to an iPad, it just strikes me as weird and wanting of that tactile keyboard). Otherwise, browsing really really feels great. Only thing I miss is the Macbook Pro style 3 finger forward/backward gestures (@AAPL plz add this before iPad2.0, and also, get iPhoneOS 4.0 to work on my iPhone 2g or at least @DevTeam plz hack 4.0 for the 2g!).

Oh, and for those lucky enough to have a magical iPad, the URL is [http://antimatter15.com/ajaxanimator/ipad/](http://antimatter15.com/ajaxanimator/ipad/) at least until there's enough testing to make sure that I didn't screw up everything with my MobileSafari hacks.
