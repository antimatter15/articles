---
title: New File Format
author: admin
date: 2007-11-17 3:01:56
categories:
  - Ajax Animator
tags: 
  - array
  - ax
  - compiler
  - file
  - format
  - javascript
  - json
  - preview
  - save
  - xml
template: article.jade
---

I'm working on a better save/preview file format, even merging the save/preview formats into one.

it's just a string seperated by ";;" before it, is a standard JSON Array. After, is the standard XML compiler stuff. the json has info like framerate,height,width,current frame, tweens, keyframes, animation length, comments?, rating?, size? etc.

the javascript save/load implementation is so far done.
