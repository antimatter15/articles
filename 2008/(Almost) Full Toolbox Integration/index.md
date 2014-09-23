---
title: (Almost) Full Toolbox Integration
author: admin
date: 2008-06-06 8:51:16
tags: 

template: article.jade
---

i have almost fully integrated&#160; the ajax animator toolbox with onlypaths. In the last post, i talked (briefly) about how i integrated the color management system. The rest was just as easy. For simple reasons, i rewrote the user statistics section of the toolbox (it took up too much room and used a switch(), so i replaced it with matching with an associative array, which is evidentally much more elegant). I also replaced the evil evals with friendlier parseFloats. 

There were tons of things that I fixed that may improve speed (ever so slightly). For some reason the application relied highly on the xyinput div. So many DOM operations obviously isn't too good when you could store all of this in a simple variable. This was a relatively minor problem.

This solved almost everything. you could switch tools, draw squares, rectangles, ellipses, circles, paths, etc. But Select failed miserably.

Still, there was a problem with the select box, so i made a quick hack. SVGRenderer apparently does direct dom operations to the page. Eventually, i'll have to track down every one of those dom operations and replace them with something scripted. But i decided to copy over the html from onlypaths html and put it inside a ext windows object. Show it, and hide it. That's why after you press &quot;enable onlypaths&quot; you may see a little box pop up and vanish&#160; almost instantly. Now select _almost_ works. it kept nagging about no document.forms[0].code. So I commented out all those lines.

I implemented a select() function to the tools. so I can dynamically select them. It used to be a sort of read-only system with the tools. The user could input to the toolbox, and that'd alter the display and change the tool (for onlypaths). but you couldn't script it to change the display. So, now it by default automatically selects the Rectangle tool when you press the magical link.

I actually don't know why I made the whole enable onlypaths thing sort of opt-in. I guess it is because its currently the least-stable part of the application. So, this prevents the app from crashing on startup (hopefully).
