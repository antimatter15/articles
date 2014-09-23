---
title: Working Animation Browser
author: admin
date: 2008-06-30 11:41:02
tags: 

template: article.jade
---

the animation browser now works. its not exactly how the production model will work, but the playback engine is in place, and so is most of the functionality. The rest is basically server code.

Go to the animations tab, and you'll see a friendly list of animations. right now, they are growsquare.js, moving.js, tradgedy.js, and spin.js. In production, you'll see discriptive, nicer titles defined from that"name:" box in the canvas toolbar.

Simply click on an animation in that browser, and through AJAX, the animation is loaded and plays automatically. You can play/pause them. and a visible button, with the icon of  a pencil, describes "import animation" which essentially lets you edit it. Click it, and you are transported to the canvas tab where the animation is loaded.

Note to self: Give warnings when loading an animation while canvas contains unsaved data
