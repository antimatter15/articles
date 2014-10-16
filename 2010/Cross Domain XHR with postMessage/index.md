---
title: Cross Domain XHR with postMessage
author: admin
date: 2010-04-20 3:01:38
categories:
  - Google Wave
tags: 

template: article.jade
---

A bit ago, I posted a little flow chart about the possibility of a Bookmarklet driven model for privledge escalation with XHR, the most important part was the postMessage based emulation of XHR, and for an offline Wave Reader that i'm working on, I needed it and created this.

In around 30 lines of code, I implemented a small subset of the XMLHttpRequest API using postMessage. While the better [pmxdr](http://github.com/eligrey/pmxdr) project does the same thing, it uses a different API. I just implemented it with the normal XMLHTTPRequest API, which isn't the ideal way anyway, but works. Notably, my code relies on json2.js unless you're relying on Native JSON and DOM Level 3 window.addEventListener.

[github.com/antimatter15/pmxhr](http://github.com/antimatter15/pmxhr)
