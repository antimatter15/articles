---
title: IE Support Progress
author: admin
date: 2008-01-24 6:06:51
tags: 

template: article.jade
---

For the billionth time, i decided to try getting IE to work.

First I patched svgrenderer.js to be more IE friendly (setAttribute instead of setAttributeNS)

Then I opened up IESVG.htc from http://starkravingfinkle.org/blog/2006/03/svg-in-ie-update/

first of all, i needed to convert that to javascript that is supported by firefox (it's hopeless developing for IE), after running a few regexps to the source code, it worked. I could dynamically convert SVG to VML. I tested it on ajax animator with a simple convert($("richdraw1").firstChild).innerHTML

since it's easier to build off a simpler (very very much) smaller codebase for a proof-of-concept, i used richdraw demo app. Since the code for richdraw hasn't been updated much, and remains implementation-independant, not requiring any other components. i loaded the script, and ran the script. I could draw on the canvas (blindly), but i could in fact draw. to check, i pressed the view-source button, and there it was: SVG code.

the drawback of this method, even if you include the SVG to VML converter, is that you will never be able to select, delete, or move drawn objects

of course, this really means nothing. I need a SVG to VML AND a SVG to VML converter.

Anyways 0.16.x releases are just supposed to be Ext 2.0 releases, not IE support releases. Maybe 0.17.x or 0.18.x, but hopefully by 0.20.0
