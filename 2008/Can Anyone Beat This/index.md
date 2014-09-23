---
title: Can Anyone Beat This?
author: admin
date: 2008-10-14 4:57:11
tags: 
  - ajax
  - function
  - librray
  - small
  - tiny
  - vX JS
template: article.jade
---

The original vX function was 337b. Now, it's been reduced down to 293 bytes, while adding a new feature (callback is now optional).
<tt>
X=function(u,f,p,x){x=window.ActiveXObject?new ActiveXObject('Microsoft.XMLHTTP'):new XMLHttpRequest();x.open(p?'POST':'GET',u,!0);p?x.setRequestHeader('Content-type','application/x-www-form-urlencoded'):p;x.onreadystatechange=function(){x.readyState==4?f?f(x.responseText,x):f:0};x.send(p)}</tt>

Apparently, the above stuff doesn't work (Wordpress?)

It's really quite amazing. The big things that reduced size were using lots of condititional things, really obfuscated unreadable stuff, and using !0 instead of true, and !1 instead of false.

If you want to use it, try building your own copy from.

[http://vxjs.googlecode.com/svn/trunk/build.htm](http://vxjs.googlecode.com/svn/trunk/build.htm)

The usage has signifigantly changed though, there, everything's namespaced under an underscore, so it's _.X("url")
