---
title: VectorEditor Updates lines, rotation, more
author: admin
date: 2009-08-10 10:23:12
categories:
  - VectorEditor
tags: 
  - chrome
  - drag
  - drawing
  - firefox
  - graphics
  - internet explorer
  - jsvectoreditor
  - lines
  - microsoft
  - opera
  - raphael
  - rotation
  - update
  - vector
template: article.jade
---

During the last two days I worked a bit on my cross platform, Raphael based vector graphics editor. It now supports Firefox, Opera, Chrome, probably Safari and magically, something called IE. Yes, it works on that nasty terror.
Really, the project started with just the idea of being able to support IE. Sure it has a few neat features (multiple select mainly), but the fundamental idea is to support IE and to do so in a stable manner.
It's actually running quite well in IE, though only the latest version has been tested.

Among the updates is a new delete tool that is far more flexible and powerful. It is now not just a button but an entire tool. So while you can still click on it to delete your current selection, you can also use the tool to click on shapes or drag and delete whole groups (not sure what that thing is called). It even has a nice red tint to signify deleting.
There is also event listening, vX support (it only uses events and position), and selecting fill, stroke, stroke opacity, fill opacity, and stroke width.

It also integrates well into the Ajax Animator in an almost drop-in replacement type. Maybe eventually something to choose between VectorEditor and Onlypaths. The really only bug features there are multiple select and drag and line editing.

Lines are now done almost perfectly. Dragging them works perfectly and it shows two little boxes on the ends that fan be dragged to edit. This vastly simplifies the old issues with lines and stick figures. Stick figures that inherently satisfy me a lot because that was the highes level of animation I ever did.

It's probably a bad thing that the developer od an animation application never did anything more complex than stick figures, and probably makes it seem strange for me to even start it. But anyone with more knowledge of animation would not be so naiive as to attempt this.

[http://jsvectoreditor.googlecode.com/svn/trunk/index.html](http://jsvectoreditor.googlecode.com/svn/trunk/index.html)
