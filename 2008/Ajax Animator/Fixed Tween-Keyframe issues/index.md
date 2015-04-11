---
title: Fixed Tween->Keyframe issues
author: admin
date: 2008-06-26 6:37:20
categories:
  - Ajax Animator
tags: 

template: article.jade
---

following the amazingly simple fixes to my issues, comes something even more radically simple. Now you can get a tween and convert it to a keyframe. It doesn't happen automagically yet (i'm working on it), but the solution to this problem is amazingly simple.

in diff.js, in the function Ax.smallest_nonempty (needs a better name, i know), on the last line, i replaced
<pre>b - a</pre>
with
<pre>a - b</pre>
It's amazingly simple.
