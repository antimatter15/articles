---
title: Progress Report
author: admin
date: 2007-10-22 10:06:56
tags: 
  - animation browser
  - animations
  - automation
  - comments
  - cross domain
  - design
  - effects
  - efficiency
  - ext 2.0
  - ExtJS
  - progress bar
  - rating
  - rewrite
  - speed
  - splash screen
  - status
  - subversion
  - timeline
  - update
  - upgrade
  - user interface
template: article.jade
---

I've not been releasing anything for a while, for several reasons:

1\. I'm converting everything to the Ext UI (from textareas, tables, etc. to Ext grids, form fields)
2\. I'm completely rewriting the timeline. including a host of new features much for speed. (several TIMES faster) mainly becuase it generates only 300 frames per layer by default, instead of 500, but automatically adds new frames DYNAMICALLY when more is needed. But the rewrite is sorta unstable
3\. Tons of UI upgrades. A short list of changes from the top of my head are, a new login stystem (lot's of fading effects) My Animations; list, faster animation loading. The user animation browser is completely changed-with stuff like Rating animations and comments coming.
4\. Sorta goes in UI upgrades, is a new loading splash screen. It has a progress bar, showing status. And CSS is dynamically added, and loads from either the local server, or google code's subversion (faster).
5\. Cross Domain Ajax. The current ajax implementation only allows you to generate flash animations if you are on a php server with all the libraries/files installed. And sometimes you go to it from a proxy or google code beta or something. If that happens, you will not have any access to creating flash animations. So, soon it will curcumvent this restriction, by using a script tag hack, to load the animations from the server. Though the current ajax implementation will still be used for larger animations. And i might revive animation compression for this purpose.
6\. Upgrading to Ext 2.0, this is not really happening NOW, but is being actively thought of. It's not really a "painless" upgrade, with lot's of stuff to modify/rewrite.
7\. Everything has two options. One is to load from subversion, or the local server. It's better if you load it from subversion, if you are mirroring it, or if your server is slow. And in many cases it's really fast, and automatically gzip encodes the stuff. Great isnt it? so it has an option of loading all* (okay, most...) images and CSS from google code.

8\. And even more stuff......
