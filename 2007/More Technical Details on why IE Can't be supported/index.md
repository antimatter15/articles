---
title: More Technical Details on why IE Can't be supported
author: admin
date: 2007-12-21 1:00:06
tags: 

template: article.jade
---

<span style="font-size: xx-small;">I'm not a really bad coder. Maybe still an amateur, but I won't just say "IE SUCKS" for no reason. It's nothing personal, really.</span>

Vector graphics allow you to draw a frame, go to another, alter it slightly (maybe moving a rectangle). It can be magnified anything from negative infinity to infinity, with sharpness, clarity of something that was designed to be viewed at. It's just like the real world, sort of. You can magnify something, and it just becomes clearer, it doesn't become fuzzier (which happens to raster formats like JPEG, PNG, BMP, TIFF, etc)

On the Web, there are three major players for vector graphics. One of them doesn't really count (CANVAS is not really vector to the extent of VML or SVG) VML is a proprietary format, created by Microsoft (this might not be true), and ONLY works in Internet explorer. There are Absolutely NO other implementations of it, WHY? Because during the draft, it was completely abandoned for SVG-a far superior format.
SVG is a standardized format for vector graphics. It is open, widely implemented and used ALOT. The flash file format is actually has a quite striking resemblance to SVG. Professionals use it, it is a standard for ALL types of vector graphics
There are at LEAST 20 times more web based SVG editors than VML. And on the desktop, there are just about no real editors for VML, but there are ones like Inkscape, Autodesk, GLIPS, Maya, Sketsa, Adobe Illustrator, Openoffice Draw, Xara, CorelDraw, Flame, Koolmoves, Microsoft Visio, xfig, just to name a few.
To me, it was almost obvious to base my file format off of SVG.
Luckily for me, the vector graphics library I used, supported both IE and the standard adhering "good" browsers. Sadly, there was one really major problem.
There was no way for someone using IE to edit/improve work of someone else using the "good" browsers. SVG can't be converted to VML.
Everything was horrible. SVG -&gt; VML -&gt; SVG??? IE support sucked. I wasted like a month trying to make a SVG/VML converter. It SUCKED. it wouldn't' render right, and often times i couldn't implement it in all the core scripts without messing everything up.
As the rest of the application progressed, IE support steadily ceased. I was about to just end support for IE. Then after several incidents with Microsoft windows, I made the "IE is not supported" error much harsher than really necessary. It was actually, because i found that an error message like that was actually nicer and friendlier than a nuclear array of error messages popping up in a consistent stream, completely making your operating freeze and the window getting unresponsive, with the only way to get out of it being to open up task manager with Ctrl+Alt+Delete (gotta love that key combo) and killing the process.

<span style="font-size: xx-small;">I tried practically everything to get internet explorer to work. I tried building a SVG-&gt;VML-&gt;SVG converter. I tried to modify an existing SVG-&gt;VML converter, I tried to trick IE to think it supports SVG (just had to go replace all namespace dom code to the standard html dom handling code, without complex namespaces) but that didn't display anyting. I tried hooking up aflax to render the SVG from within flash (sorta worked... no color). Everything I tried didn't work out very well.
If Internet Explorer, just Magically supported SVG, it would probably just work. It would just simply work in the way it does in any other browser.</span>
