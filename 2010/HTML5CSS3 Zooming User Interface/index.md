---
title: HTML5/CSS3 Zooming User Interface
author: admin
date: 2010-08-29 1:39:34
tags: 
  - interface
  - pan
  - spatial history
  - wheeeee
  - zoom
  - zui
template: article.jade
---

<object style="height: 344px; width: 425px;" classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" width="100" height="100" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,40,0"><param name="allowFullScreen" value="true" /><param name="allowScriptAccess" value="always" /><param name="src" value="http://www.youtube.com/v/Zus6yre73Qc?version=3" /><param name="allowfullscreen" value="true" /><embed style="height: 344px; width: 425px;" type="application/x-shockwave-flash" width="100" height="100" src="http://www.youtube.com/v/Zus6yre73Qc?version=3" allowscriptaccess="always" allowfullscreen="true"></embed></object>

I'm taking liberties with the [concept of zooming user interfaces](http://en.wikipedia.org/wiki/Zooming_user_interface), but this is an example of something that lets you browse wikipedia by zooming in toward a link, and zooming out to go back. So I guess it's more of a z-axis spatial visualization for history somewhat similar to what I guess Apple's Time Machine program is like (though I have never tried it).

It uses html5's popState and pushState to get the URL to change without reloading the page (which, btw people should use instead of the weird /#/ urls). It uses webkit transformations, which probably aren't part of CSS3 since it's vendor specific, but I haven't had time to hack it to work on firefox, [feel free to fork](http://github.com/antimatter15/zui/blob/master/zui.js).

[Zoomify](javascript:(function(){var scale=1,tx=innerWidth/2,ty=innerHeight/2,sx=innerWidth/2,sy=innerHeight/2;document.onmousewheel=function(a){if(a.wheelDelta){if(a.wheelDelta&gt;0)scale*=a.wheelDelta/100;if(a.wheelDelta&lt;0)scale/=-a.wheelDelta/100}scale&lt;0.05&amp;&amp;history.go(-1);showTransform();a.preventDefault()};window.onpopstate=function(a){loadPage(a.state.url)}; function showTransform(){document.body.style.webkitTransform=&quot;scale(&quot;+scale+&quot;) translate(&quot;+(innerWidth/2-tx)+&quot;px,&quot;+(innerHeight/2-ty)+&quot;px)&quot;;var a=document.elementFromPoint(innerWidth/2,innerHeight/2);if(a.nodeName==&quot;A&quot;&amp;&amp;a.offsetWidth*scale&gt;0.3*innerWidth&amp;&amp;a.offsetHeight*scale&gt;0.3*innerHeight){console.log(&quot;clicky&quot;);loadPage(a.href);history.pushState({url:a.href},a.href,a.href)}} function loadPage(a){var b=new XMLHttpRequest;b.open(&quot;get&quot;,a,true);b.onload=function(){document.body.innerHTML=b.responseText;showTransform()};b.send(null);scale=1;tx=innerWidth/2;ty=innerHeight/2;sx=innerWidth/2;sy=innerHeight/2;showTransform()}var dragging=false;document.onmousemove=function(a){if(dragging){tx+=(sx-a.pageX)/scale;ty+=(sy-a.pageY)/scale;sx=a.pageX;sy=a.pageY;showTransform();a.preventDefault();a.stopPropagation()}}; document.onmousedown=function(a){dragging=true;sx=a.pageX;sy=a.pageY;a.preventDefault()};document.onclick=function(a){a.preventDefault()};document.onmouseup=function(a){dragging=false;a.preventDefault()};})())

So that's a bookmarklet. feel free to click it on this site and it'll get rid of the infinite scrolling and for some reason it doesn't work well on this site. Try it on wikipedia.
