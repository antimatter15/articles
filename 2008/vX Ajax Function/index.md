---
title: vX Ajax Function
author: admin
date: 2008-10-07 9:01:03
categories:
  - vX JS
tags: 
  - ajax
  - fast
  - function
  - get
  - light
  - post
  - vX JS
template: article.jade
---

For one of my projects, I needed a really simple, lightweight one. It's super lightweight. I mean really. really lightweight. Only 337 bytes (though 1 kilobyte of random crap in front of it would make it 1337 bytes). Most libraries are over 60kb! If you're using it _only_ for ajax. You're using 180 TIMES what you really need.

This one can do GET/POST requests with a callback

<tt>/*vX Ajax Function. (C) Antimatter15 2008*/
function vX(u,f,p){var x=(window.ActiveXObject)?new ActiveXObject("Microsoft.XMLHTTP"):new XMLHttpRequest();
x.open(p?"POST":"GET",u,true);if(p) x.setRequestHeader("Content-type","application/x-www-form-urlencoded");
x.onreadystatechange=function(){if(x.readyState==4&amp;&amp;x.status==200) f(x.responseText)};x.send(p)}</tt>

It takes 3 parameters. the URL, the Callback function, and the post parameters (optional).<tt>
vX(AJAX URL, CALLBACK FUNCTION[, POST PARAMETERS]);
</tt>
Note that here the callback is required, not optional, though it could probably be made to do that by changing f?f(x.responseText):x.

To Use:

GET:
<tt>vX("ajax.php?you=suck&amp;howmuch=alot", function(responsetext){alert(responsetext)})</tt>

POST:
<tt>vX("ajax.php", function(responsetext){alert(responsetext)}, "you=suck&amp;howmuch=alot")</tt>

That's it. In case your wondering what the name is, I wanted somethign that was short so it was lightweight. I didnt want it to be single letter because single-letter names are likely to collide with other libraries. Also because "V" and "X" are two widely overused characters anyway. Another reason might be that you dont know what version it is :P
