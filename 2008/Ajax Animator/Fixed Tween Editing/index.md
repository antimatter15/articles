---
title: Fixed Tween Editing
author: admin
date: 2008-06-26 7:04:48
categories:
  - Ajax Animator
tags: 

template: article.jade
---

now it automatically converts tweens to keyframes the moment you edit them. The problem was because the tweening engine had virtually infinite percision so, lets say that one fo the calculations ends up like 22/7 which computes to 3.142857142857142857142857142857142857142857142857... somewhere along the process of loading it into onlypaths, doing freaky stuff, processing, parsing, unparsing, converting, parsing again, and something, things get rounded to 3.1428\. The simple fix was to round them from within the tweening engine. So it gets rounded to 3.142, and it works.
