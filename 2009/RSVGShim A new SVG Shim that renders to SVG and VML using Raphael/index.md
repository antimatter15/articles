---
title: RSVGShim A new SVG Shim that renders to SVG and VML using Raphael
author: admin
date: 2009-09-04 2:43:53
categories:
  - Ajax Animator
  - VectorEditor
tags: 
  - graphics
  - raphael
  - shim
  - SVG
template: article.jade
---

For like an hour (so, not a really long time, and nothing near SVGWeb) or so, I was working on a new SVG shim similar to SVGWeb except that it renders to VML and SVG through Raphael rather than Flash (so now I can actually brag about not having *any* plugins :P). Using it is somewhat simpler than SVGWeb, except that you need some replacing, but no need for a server, htcs, etc. Plus, the file is only 3.2 kb uncompressed, only 740 bytes gzipped and YUI'd. Also, it only works with rectangles and ellipses but could be somewhat easily modified to support anything that raphael does. While probably it does not work on IE (as I use linux and have no way to test), it's an interesting concept.

It only works with pages where a SVG element is added dynamically after the page is loaded (contrasting to SVGWeb which only allows a SVG element to be added in code).


	var svgroot = rshimdoc.createElementNS(null, "svg"); //you coudl also just use normal createElement("svg"), but it must be rshimdoc instead of document

	svgroot.setAttribute('width',100); 
	svgroot.setAttribute('height', 100);


	(new RHTMLElement(html element)).appendChild(svgroot)


OR


	rshimdoc.getElementById(element id).appendChild(svgroot)
	
So it doesn't deviate too much from the SVG spec (just replacing document with rsvgdoc should work). And in other news, I'm moving some of my smaller works to github, so this project is also going to be hosted on GitHub.

[http://github.com/antimatter15/rsvgshim/tree/master](http://github.com/antimatter15/rsvgshim/tree/master)
