---
title: Desktop Flash IDE ForkSwif Released
author: admin
date: 2008-01-23 6:05:52
tags: 
  - .net
  - ajax animator
  - c#
  - c-sharp
  - draw
  - forkswif
  - liveswif
  - mono
  - prototype
  - timeline
  - vb.net
  - visual basic
  - windows
template: article.jade
---

This was a really small project of mine. It is (going to be) open source, but I’ll probably never work on it again. It has a much larger number of tools than Ajax animator. The editing will be much a relief, and so much better than rich draw. Sadly, it has no tweening, frame duplicating, effects, or any of the features in Ajax animator.

It is currently only for Windows with .net framework 2.0 installed, Mono/Wine is not tested (but Mono has to be used with wine, as it calls swfmill.exe (win32 binary) for flash generation.

About the name:Liveswif has been a great piece of software, probably the best (free) flash IDE ever. Sadly, it has been discontinued for since years ago. The community has been working on something called "OpenSwif" it was supposed to be the successor to the famed liveswif. The problems were, that liveswif was proprietary (freeware), so they had no codebase to begin on. Ajax Animator started out as something for the developers of OpenSwif to get inspiration off of, and just one of my random ideas. As of now, OpenSwif still has no released imagery/source/binaries; there is only one developer, and no signs of active development. I just decided one day, discovering some information to be mentioned in the next paragraph, that I could really do things a lot better than they were doing now. I, for once, actually utilized the wonders of open source, forking. As everyone on the OpenSwif team were acting as if OpenSwif was proprietary.

I, reading up on swfmill, discovered it had something called SVG import, meaning, it could read a svg file to convert into SWF. With this realization, I quickly searched VB.NET (my first programming language, btw, but I like JS more now) SVG Editor. Too much dismay, no VB.NET SVG editors existed, but I found one coded in C#. I made a TODO list that basically said: Make Timeline, Attach Timeline, Hack SVG Paint, and attach Swfmill. It was with much less work than I expected. Being a crappy c# coder, I made most of it in VB.net, and converted it to c# (using online tools). The timeline was pretty easy (20 lines of vb code), which fit easily on the SVGPaint layout. Then I hacked the saving mechanism to save automatically (without user interference), which was as simple as deleting all the references to message boxes (well, in docmanager.cs). I built a quick and dirty swfmill launcher program that generated the necessary markup. And sadly, it didn’t work. After a bit of experimentation, I discovered that you have to attach an ID to every svg element, which the program didn’t do. I just had to add “id=shape”+rand.Next(9999999).toString() somewhere and voila, I finished the flash ide. All in less than 50 lines of code. Now all I needed to do is to rebrand it (evilest, no…um… I mean easiest part).

In retrospect, I probably wrote more in this essay (article or whatever) than all the work I spent on the ForkSwif project.

Read more at:

http://www.pryjon.com/liveswifers/forums/viewtopic.php?t=1377
http://www.pryjon.com/liveswifers/forums/viewtopic.php?t=1364
http://code.google.com/p/forkswif/

What the heck is wrong with me and writing such long essays for random news topics?!?! I should spend this effort on homework.....
