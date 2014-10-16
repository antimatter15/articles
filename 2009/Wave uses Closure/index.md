---
title: Wave uses Closure
author: admin
date: 2009-11-08 5:27:38
categories:
  - Google Wave
tags: 
  - closure
  - magic
  - omgoogle
  - wave
template: article.jade
---

Closure Tools were [recently released](http://googlecode.blogspot.com/2009/11/introducing-closure-tools.html) by Google to allow for others to use the same rich libraries that Google uses internally. Its used by Gmail, Google Docs and Google Maps, but interestingly also used by Google Wave. While they don't actually announce that Closure is used in Wave, the view-source obfuscated mess from Wave does strongly show it.The reason why its use in wave is more interesting than most others is that Wave is in GWT, while the rest are pure JS. This implies that an interface to the Closure Library may be coming to GWT. While the interface doesn't seem to be made from Closure, there are references to "closure_hashCode" and "goog.net.BrowserChannel".
