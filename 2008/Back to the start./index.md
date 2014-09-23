---
title: Back to the start.
author: admin
date: 2008-06-19 9:19:04
tags: 

template: article.jade
---

I've decided to rework the tweening system. The entire animation system.

I designed it so any frame is editable. When you edit it, it becomes a keyframe automatically, and then everything magically tweens itself. Now it gets complex. What happens whne you edit a tween? How does that work?

Well, first of all, this is how the diff-system works. It gets two frames and compares every element, attribute by attribute for any differences. Any differences means its not the same thing, and it becomes a keyframe. Then during the tweening process, all those inbetween frames (tweens) are flagged a tween. When flagged a tween, the diff system just ignores them and jumps to the keyframe before them. So what if you edit a tween? Once the tween is recalculated, your changes are lost *forever*. So how do I fix this? I don't know. I may have to make it so the frame is masked and blocks user-interaction, put a little warning up saying "omg! this is a tween!" or something.
