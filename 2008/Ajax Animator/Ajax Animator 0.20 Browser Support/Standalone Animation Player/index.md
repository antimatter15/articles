---
title: Standalone Animation Player
author: admin
date: 2008-07-16 8:31:57
categories:
  - Ajax Animator
tags: 
  - animation
  - player
  - standalone
template: article.jade
---

I've created an animation player. It works with all ajax animator animations, and when compressed is a mere 3kb (which I believe is lower than OnlyPath Viewer).

It is built using the very same sources of the Ajax Animator, the whole purpose of all those *_core.js files. It uses the files
Ext.ux.clone.js, op_view.js, svgrenderer_mini.js, vmlrenderer_mini.js, wrapper_core.js, view_wrapper.js, and tween_core.js.

svgrenderer_mini.js when compressed is just over 1.1kb and same is for vmlrenderer_mini.js

I'm on my linux development environment now, so I haven't tested it in IE, but it will 100% fail, as the rendering engines is not detected and it uses SVGRenderer always.

See it in action here:
http://ajaxanimator.googlecode.com/svn/trunk/ajaxanimator/html/player.htm
