---
title: Status Fixing the compiler problem
author: admin
date: 2008-06-07 1:14:35
categories:
  - Ajax Animator
  - OnlyPaths
tags: 
  - arrangement
  - compiler
  - onlypaths
  - vml
  - vmlrenderer
  - working
template: article.jade
---

I've located part of the problem. If I remove the reference to VMLRenderer.js, it suddenly starts working again. But how do I include it and get it to work still. I'm investigating.

EDIT 1:

Build 117 fixes the problem completely. it was simply because of mis-arrangement of the files. It was originally.
<pre class="csharpcode">...
  <span class="kwrd">&lt;</span><span class="html">script</span> <span class="attr">type</span><span class="kwrd">="text/javascript"</span> <span class="attr">src</span><span class="kwrd">="../js/drawing/onlypaths.js"</span><span class="kwrd">&gt;&lt;/</span><span class="html">script</span><span class="kwrd">&gt;</span></pre>
<pre class="csharpcode">  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/wrapper.js"</span>&gt;<span class="kwrd">&lt;/</span><span class="html">script</span><span class="kwrd">&gt;</span> 
  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/svgrenderer.js"</span>&gt;&lt;/script&gt;
  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/vmlrenderer.js"</span>&gt;&lt;/script&gt;
...</pre>
<pre class="csharpcode"></pre>
for some reason, this messed up the compilier. I changed it to.
<pre class="csharpcode">  <span class="kwrd">&lt;</span><span class="html">script</span> <span class="attr">type</span><span class="kwrd">="text/javascript"</span> <span class="attr">src</span><span class="kwrd">="../js/drawing/onlypaths.js"</span><span class="kwrd">&gt;&lt;/</span><span class="html">script</span><span class="kwrd">&gt;</span>
  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/svgrenderer.js"</span>&gt;&lt;/script&gt;
  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/vmlrenderer.js"</span>&gt;&lt;/script&gt;
  &lt;script type=<span class="str">"text/javascript"</span> src=<span class="str">"../js/drawing/wrapper.js"</span>&gt;<span class="kwrd">&lt;/</span><span class="html">script</span><span class="kwrd">&gt;</span></pre>
<pre class="csharpcode"></pre>
<span class="kwrd">and now it works fine :) </span>
