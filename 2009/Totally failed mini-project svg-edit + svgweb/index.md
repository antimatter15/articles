---
title: Totally failed mini-project svg-edit + svgweb
author: admin
date: 2009-08-24 7:01:05
categories:
  - Ajax Animator
tags: 
  - google
  - svg-edit
  - svgweb
template: article.jade
---

So I tried to get svg-edit to work with svgweb's flash shim (IE support). Sadly, it's a total failure!

[http://antimatter15.com/misc/svgweb-svgedit/svg-editor.html?svg.render.forceflash=true](http://antimatter15.com/misc/svgweb-svgedit/svg-editor.html?svg.render.forceflash=true)

I only got far enough to get drawing lines, paths, polygons and rectangles working. Ellipses and text do not work. Selecting a shape shows the tracker, but if you drag it then it just flies over to (0,0) and dies. Partly because I didn't spend any more than an hour getting the port to work, but the issues I've encountered is that svgweb doesn't implement shape.getBBox() (but it did provide shape._getX(), shape._getY(), shape._getWidth(), and shape._getHeight() so it wasn't hard to implement that). Then was that since it's using a flash shim, the events which they hook on the container with jQuery only show the evt.target as the &lt;embed&gt; which the flash resides in. But I got a strange hack where you have 2 copies of the event listeners and kill the selects from the jQuery one, but doing that makes unselecting impossible.
