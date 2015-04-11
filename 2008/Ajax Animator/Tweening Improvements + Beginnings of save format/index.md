---
title: Tweening Improvements + Beginnings of save format
author: admin
date: 2008-06-24 9:19:34
categories:
  - Ajax Animator
tags: 

template: article.jade
---

oh yeah! 
Sadly, one big problem is with editing tweens. It doesn't work at all. I don't know why. Ideally, when you edit a tween, it instantly becomes a keyframe (as expeted) and magic happens. Somehow, it's not so.

The beginnings of the save format, horrendously codenamed "ALEON" is starting. Its remarkably simple actually. The implementation was, i don't know, 10 lines (including whitespace), i'll just post it here.

Ax.export_animation = function(){
  var layers = {};
  for(var layer in Ax.layers){
    layers[layer] = {
      keyframes: Ax.layers[layer].keyframes,
      src: Ax.canvas_storage[layer]
    }
  }
  return {
    /*insert metadata here*/
    layers: layers
  }

it's actually quite complete. Most things should work fine. I just gotta build a loader for it, which I expect to be similarly minimalistic.
}
oh, whoops! i left that curly brace all by its own :P 
