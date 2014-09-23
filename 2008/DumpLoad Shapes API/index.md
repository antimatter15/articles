---
title: Dump/Load Shapes API
author: admin
date: 2008-06-07 4:15:21
tags: 

template: article.jade
---

I basically ported the JSONRDF format over to the ajax animator. The code is much condensed.

To dump the canvas, try Ax.dumpshapes("json"). to load it, use Ax.loadShapes(insertjsonstringhere). Ax.dumpshapes("array") returns an array that can also be loaded by Ax.loadShapes.
