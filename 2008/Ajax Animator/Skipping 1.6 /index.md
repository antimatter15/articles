---
title: Skipping 1.6 
author: admin
date: 2008-04-13 7:12:48
categories:
  - Ajax Animator
tags: 

template: article.jade
---

I'm gonna skip version 1.6 and go straight to 7\. I'm gonna have to change my roadmap a bit, as the next version will have a *completely* redesigned interface.

Partially due to the switch from the ext 1 to ext 2 default theme, but also because of some new features, making better use of screen estate, and making things more intuitive.

And a short rant:
[rant]
Firefox *is* and operating system. Whether you think of it or not, its a fully fledged operating system. What sucks, is that it is that it is running ontop of another operating system (say, windows). We all know that *most* operating systems are terribly bloated and slow. Windows (the second os i'm using now) and Firefox (my OS) are not necessarily the most optimized, streamlined, fast, and un-bloated systems out there. I'd consider them the most bloated operating sytems possible. So any Web 2.0 app is coded in a highly unoptimized interpreted language. Not only, you have to hack it several times just to get it to do something cool. So, interpreted languages already are infamous for their speed-- combine that with the two slowest operating systems out there, layered, and what do you get? you get a horrifying piece of crap.

Note: this is probably flamebait, but i actually do consider IE to be slower than firefox. I pity everyone who still uses it, and i'll pity you even more when you realize how unbearably slow Web 2.0 apps are on there-- and i wouldn't count on IE 8 improving that, benchmarks report that IE 8 is slower than IE 7/6 respectively.
[/rant]

I dont have any screenies so....

Redesigned timeline layout. Sorta looks like a clone of Adobe's but different at the same time.

Its no longer the "history" tab (on the east panel). Its now the "Misc" tab, and it contains an accordian panel.
The panel has 4 subpanels:
-History, which is the same Ext grid as in the current version
-Clipboard: I currently have a simple one-dimensional Copy/Paste system. The new version will have a History-like clipboard manager, with infinite storage (crap! i'm killing the least efficient platform evah!).
-Library: The new version will support a general clipart libary. It is filled with simple vectorized graphics. I'm invisioning a community-generated/organized tree-view with folders catagorizing the thing. and a drag/drop interfacing for using them.
-Misc: misc. i donno whats gonna go here. maybe a "don't press this button" button that counts how many people pressed that button :P

The center panel, traditionally divided into two segements, Canvas and Preview (adobe only has canvas), will now be orgainized into three. The Canvas, Preview are still there, and an added one is the "Animations" tab. The animations tab is where users can view, play, import other users's animations. It is a way to encourage collaboration, innovation, and to generally make it more intutive.

Not just the user-interface will be modified. but the application will be practically rewritten. It will switch from MD5 to SHA1 passwords. and the greatest change in project history: Transitioning out of RichDraw

It has become apparent that Richdraw is quite incompetent. There is no interoperatability between the rendering engines (read: IE can not collaborate with Firefox/Safari/Opera). It has poor abstraction of the drawing format, so modifications to the canvas are normally done directly with the format. It has no documentation whatsoever, and its capabilities are very limited. It has no support for alpha transparency, no paths, images,text, scaling, panning, clipboard,z-index, groups, and much more horrific details.

There are two projects that can improve on this issue. One, is OnlyPaths by a member of this site, josep_ssv. OnlyPaths is based on richdraw, but fixes it alot. It is a very active, new project, and has reached outstanding feature set already. I contributed to the project some (i wrote the save format, and submitted some patches). There is only one problem with OnlyPaths: Browser Compatability. Its a sort of SVG R/W and VML RO system. Basically, SVG enabled browsers can draw, and save to full extent, meanwhile IE can import but not export. IE support is basically that of Richdraw.

The second project is Prototype Graphic Framework (or Class) (aka PGF/PGC). It is not as active, and has not been updated in quite a while, but it has superior docuemntation, a nice API for transformations, a Canvas renderer and is very stable, mature and powerful. its disadvantages are that its not a very active project, with some half-baked features, lacks PATH support, and has no real editor component.

After lots of thought, I've decided to use Prototype Graphic Framework for this version. Mainly because of browser compatability, and that PGF is much more mature. But the transition to OnlyPaths is inevitable in the near future when it is better with browser compatability and becomes more mature.

I've decided to use polylines rather than paths becuase of ease of porting the drawing engine to polylines and because polylines work better with cross-browser.

At first, i looked for a way for IE to use SVG, but once i realized that what I really needed to do was to create an entirely new format supported by both rendering methods. I used JSON (JavaScript Object Notation) for the format, as it is very portable, fast, and the native format of javascript. Basically it is a set of instructions for what to tell the drawing API to draw.
