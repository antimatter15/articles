---
title: JS vs Python
author: admin
date: 2009-08-27 4:01:36
categories:
  - Uncategorized
tags: 
  - chrome
  - fast
  - google
  - python
  - speed
template: article.jade
---

I sorta expected it due to the new V8, Tracemonkey, Nitro, and SquirrelFish engines. But I'm thinking of making a port of ShinyTouch to JS and I was looking into what differences it might end up as.

I have to say I'm really quite suprised. It's a simple piece of code:
`
setTimeout(function(){
var start = (new Date).getTime();
var n = 0;
for(var i = 0; i &lt; 10000000; i++){
n += i;
}
var end = (new Date).getTime();
alert(end-start);
},5000)`
Just doing a loop a huge number of times and adding some numbers. But the unscientific results are quite amazing:

Python: 2640, 2110, 2000, 2190

Firefox 3.0 Spidermonkey: 777, 672, 685, 665

Firefox 3.5 TraceMonkey: 659, 365, 629, 629

Chromium Nightly: 146, 150, 147, 152

While these only test basic arithmetic and recursion, _The browser_ is 15 times _faster_ than Python, it just feels quite incredable.
