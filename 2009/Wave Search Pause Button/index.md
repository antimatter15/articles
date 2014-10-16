---
title: Wave Search Pause Button
author: admin
date: 2009-11-06 10:06:07
categories:
  - Google Wave
tags: 
  - wave
template: article.jade
---

An issue now with the floods (is there any post about wave complete without a pun?) of people in wave, the with:public channel (of waves!) is becoming a unusable tsunami (har har har) of waves where clicking on one will end up opening up something else totally randomly as it has shifted down several by the time you click it.

So what is there to stop it? Well, I made this insanely great, floodwall: the Wave Pause button. It's a simple bookmarklet that if you click, it stops all incoming updates to the search panel and clicking it again restores it.

The functional bookmarklet can be found at http://antimatter15.com/misc/wave/pause.html which is a rather hideous looking page hacked together quickly.

How does that work? Well, it turns out it's actually not that easy. My first idea was to just find the function which updated things (it turned out to be Vwh) and replace it with function(){} and restore it later. That worked fine... But I remembered some evil crap that google said, about GWT source being browser-targeted. Incidentally that means Wave gets dfferent versions of the code with different function names, and if they ever update wave, all the function names screw up too!

Oh noes! What now? Well, it uses a sort of pseudo-heuristic approach. It searches for a big characteristic which is .style[w2g]. BUUT, w2g is fwg in chrome! So first it iterates through all variables and finds one whose value equals "display". Then it takes that variable name, and searches for functions which have .style[name of string which equals display] twice. That reduces the pool significantly. Then it checks to make sure it has the string .innerHTML in it, and has 4 arguments. After that, well, you are reduced to a single function and you can use the same method described above.
