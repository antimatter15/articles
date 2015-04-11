---
title: IE somewhat works
author: admin
date: 2008-07-29 9:23:14
categories:
  - Ajax Animator
tags: 
  - internet exploder
  - vml
template: article.jade
---

I just discovered the source of virtually all the IE problems: the non functional VMLRENDERER.prototype.info() function. I managed to implement part of it, and magically, IE works a bit. Its nto very stable, and the tween engine gets weird errors all the time.
