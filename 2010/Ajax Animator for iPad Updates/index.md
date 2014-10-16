---
title: Ajax Animator for iPad Updates
author: admin
date: 2010-06-17 6:38:19
categories:
  - Ajax Animator
tags: 
  - ajax animator
  - ipad
  - vectoreditor
template: article.jade
---

This isn't really new, but I just remembered to write a post about it. [Ajax Animator for iPad](http://antimatter15.com/ajaxanimator/ipad/) got a relatively minor, but certainly pretty important update.

The new update incorporates the [TouchScroll j](http://github.com/davidaurelio/TouchScroll)avascript library to have nice flick-to-scroll-ness throughout native iPad apps.

The[ VectorEditor](http://jsvectoreditor.googlecode.com) core had a few bug fixes, rotation now works and so does resizing (though it's still susceptible to the[ always-existent resizing of rotated objects awkwardness](http://code.google.com/p/jsvectoreditor/issues/detail?id=1) - I would love it for someone to [fix it](http://code.google.com/p/jsvectoreditor/source/browse/trunk/editor.js#383)). However, resizing doesn't change the size of the bounding box, which is a somewhat awkward aesthetic but it's still functional.
