---
title: New Tweening Engine?
author: admin
date: 2008-07-09 1:39:25
tags: 

template: article.jade
---

I may have to create a new tweening engine for the Ajax Animator. It will end up having to change the file format and several others as well (It will be similar enough to the current system, so a conversion utility would be simple).

The necessity of this arises from a very simple design issue.... and my laziness. I designed the ALEON format to use this type of format, but it was abandoned early in the implementation as the OPF system was much simpler.

The idea was that a frame would be stored as an object with the shape id as the identifier such as:
<pre>{"shape:blah-blah-blah":{type: "rect", stuff...}}</pre>
In practice, it ended up something like
<pre>[{id: "shape:blah-blah-blah", type: "rect", stuff...}]</pre>
which may be somewhat simpler to implement, and is a bit more logical/consistant, and perfectly fine in an OnlyPaths environment, it is not as good for a tweening environment.

To demonstrate the issues with this design, try making an animation in the ajax animator with 4 shapes. Now go to another frame, and delete the middle one. What happens, is that the frame doesn't disappear, but rather, the deleted shape gets morphed into the next shape, and the last shape is deleted.
