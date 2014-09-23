---
title: Javascript Distributed Computing + Google App Engine
author: admin
date: 2008-06-12 4:41:17
tags: 

template: article.jade
---

Okay, so I've ported my distributed computing project over to GAE/Python with tons of new features, the hashes are no longer hard-coded, things are loaded from a queue. It murders caches so Opera and Safari work. You can submit a new hash to process, view the current queue and "bury" (send to the lowest priority) items you don't like (or just take too long). And because its Google, you know its quite fast. The MD5 script is now 1/3 of the original size and the main script is 100 bytes smaller (in other words, 20%).

Try it out here: http://jsdc.appspot.com/
Source at: http://js-distributed-computing.googlecode.com

&nbsp;
