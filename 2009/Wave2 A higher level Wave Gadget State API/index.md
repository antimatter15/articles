---
title: Wave2 A higher level Wave Gadget State API
author: admin
date: 2009-08-17 5:26:20
categories:
  - Ajax Animator
  - Other
tags: 
  - api
  - gadget
  - google wave
  - googlewave
  - library
  - wave
template: article.jade
---

I was working on a new little Wave State API update. It supports lists in the form of subkeys, and something very much like hierarchy and events on specific sub-nodes. This way you don't have everything update (someone's edits on frame 36 doesn't matter if you're on frame 42).

Everything is namespaced under a singleton global, wave2\. It includes functions like

*   listen (execute a callback when something beginning with the prefix is changed)
*   ignore (un-listen),
*   keys (shortcut for wave.getState().getKeys()),
*   subkeys (get keys which begin with a certain prefix, important to the pseudo hierarchy),
*   set (submitdelta with first arg as name and second as value),
*   get (shortcut for wave.getState().get()
*   reset_gadget (a simple way to empty all the data in the store)
And since it's quite short, I'm putting it under public domain at http://antimatter15.com/misc/wave/wave2.js
