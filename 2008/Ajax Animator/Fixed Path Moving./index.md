---
title: Fixed Path Moving.
author: admin
date: 2008-07-03 6:40:25
categories:
  - Ajax Animator
tags: 

template: article.jade
---

I fixed the way you moved paths, it was really simple, I changed 

var xinc = left-xshe;
var yinc = top-yshe;

to 

var xinc = left-box.x;
var yinc = top-box.y;

So paths can be moved correctly now. I also changed the default grid size to 5px rather than 15px
