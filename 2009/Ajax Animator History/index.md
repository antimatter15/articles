---
title: Ajax Animator History
author: admin
date: 2009-7-12 22:24:04
categories:
  - Ajax Animator
tags:
  - history
  - retrospective

template: article.jade
---


The Ajax Animator project started in early 2007, when I was in 6th grade. It was spawned by my interest in Flash in 2005 (because I liked expression by stickfigures and animation, and that it was one of the few ways to make applications or media for the Sony PSP) and my reluctance to pirate the Flash software after the trials expired. This intrest brought me to the liveswifers forum, which was engaging on a (as of yet and then) vaporware called OpenSwif. The idea for the Ajax Animator started when I was talking to a friend about a software program he used called Koolmoves. After making a forum post titled "Web 2.0 Flash IDE", the project really started.

The development started based on <a href="http://starkravingfinkle.org/blog/2006/04/richdraw-simple-vmlsvg-editor/">RichDraw</a>. It actually started out as RichDraw with a different layout. It was for a very long time built around the HTML/CSS/JS that was included in the RichDraw Demo. I never really modified RichDraw while using it, just building around it. I added a "timeline" (not at that time functional) which was just a dynamically generated table counting from 0-100. I added more stuff, looking for random cool scripts that made windows, dialogs, and color pickers.

Eventually, I found <a href="http://www.dhtmlgoodies.com/">DHTML Goodies</a> (mostly for it's color picker widget), and then used it's DHTML Suite to rewrite the entire application. After it was rewritten, It still was totally disfunctional. I added support for manual frame-by-frame animation and then Flash export thanks to <a href="http://freemovie.sourceforge.net">freemovie</a>. Around this time, I made a Google Code project for it and began using SVN.

After looking thorugh the DHTML Suite page, I found a link to another library called <a href="http://extjs.com">ExtJS</a>. I ported from the DHTML Suite to ExtJS 1.0. Then I versioned it 1.0. I added some pretty neat features, like tweening, sharing, and more.

Later, when ExtJS 2.0 came out, I began developing the next version of the Ajax Animator. Also, realizing how incomplete the project was, the versioning scale was changed and it was now developing 0.20. It was a full rewrite from scratch. During development Ext 2.1 came out so development migrated to that version. This version polished things up a lot with newer development paradigms and a new vector drawing editor called OnlyPaths, contributed by josep_ssv. It had a new cross-platform JSON based serialized graphics format, and supported export to many different formats. One feature that was never ported to 0.2 was support for user accounts and server side storage.