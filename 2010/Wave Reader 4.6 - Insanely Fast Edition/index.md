---
title: Wave Reader 4.6 - Insanely Fast Edition
author: admin
date: 2010-01-14 11:08:01
tags: 
  - fast
  - google wave
  - javascript
  - wave
  - wave reader
  - woot
template: article.jade
---

Loading a 500 blip wave in Google's GWT Client takes 3:34 to get to a usable state (Where the scroll bar works) on a 3ghz Core2 Duo (whose extra core admittedly won't do much). It also uses 972 MB of RAM.

Loading the same wave in my Wave Reader, take**s 678 milliseconds. A 315x speed-up**. Also, my client is totally unoptimized, pure 30KB of javascript. On top of those features, **anyone can view waves<span style="font-weight: normal;">, without a google account, </span>individual blips can be linked **to, it supports rendering almost everything Wave can, that is **gadgets, inline replies, nesting, **font color/size, italics, bold, everything you could probably expect. Interestingly, when you add an attachment to Wave, and delete the parent blip, it still stores the attachment on the current wave state, and this client can display/link to them without using Playback. There is an option to **generate plain simple HTML** for turning a Wave into a standalone page or Website. **Private waves can be exposed read-only as a website** simply by adding the gwavereader@googlewave.com username.

Using it is simple, take  a Wave https://wave.google.com/wave/#restored:wave:**googlewave.com!w%252Br5lewFqCA** and then put it after the Wave Reader URL http://antimatter15.com/misc/wave/read.html?**googlewave.com!w%252Br5lewFqCA**
And magically you have a super awesome URL to link to.

You can learn some tricks on how to use it to do some more awesome things [http://antimatter15.com/misc/wave/read.html?googlewave.com!w%252BrnG0vaFXA](http://antimatter15.com/misc/wave/read.html?googlewave.com!w%252BrnG0vaFXA) such as the before mentioned HTML generation.

Samples (Some random waves):
[http://antimatter15.com/misc/wave/read.html?googlewave.com!w%252Br5lewFqCA](http://antimatter15.com/misc/wave/read.html?googlewave.com!w%252Br5lewFqCA) (New for 4.6 Inline reply support)
[http://antimatter15.com/misc/wave/read.html?Ze3l0mj0A](http://antimatter15.com/misc/wave/read.html?Ze3l0mj0A)
[http://antimatter15.com/misc/wave/read.html?oPg9HfEXE&amp;beta](http://antimatter15.com/misc/wave/read.html?oPg9HfEXE&amp;beta)
[http://antimatter15.com/misc/wave/read.html?Mu9eK7j2H](http://antimatter15.com/misc/wave/read.html?Mu9eK7j2H)
[http://antimatter15.com/misc/wave/read.html?AhbL5fooD&amp;beta](http://antimatter15.com/misc/wave/read.html?AhbL5fooD&amp;beta)
[http://antimatter15.com/misc/wave/read.html?googlewave.com!w+UDMZOGpSG](http://antimatter15.com/misc/wave/read.html?googlewave.com!w+UDMZOGpSG)
