---
title: JS Distributed Computing
author: admin
date: 2008-05-26 3:41:20
tags: 

template: article.jade
---

A few months, i attempted something called "Distributed Computing". There are many distributed computing projects. Some big ones are Folding@Home, SETI@Home, and everything [else](http://en.wikipedia.org/wiki/List_of_distributed_computing_projects). These have a relatively small user base. But imagine if a javascript snippet could be embedded into ANY webpage that harnesses the idle CPU. Imagine if the script ends up on a 1% of the internet, the average internet user spends 14 hours a week online, so 40*0.01 is .14 hours (8.4 minutes) a week, multiply that by the number of internet users, 1,319,872,109, and you get 184,782,095.3 a WEEK, multiply that by 52, and get 9,608,668,954\. That's 9.6 BILLION hours of computing time you get in a YEAR.

The chances of anyone noticing the script running is slim. Its not nearly as efficient as those other computing platforms. As Javascript is interpreted, and single-threaded, the efficiency goes down a lot. To demonstrate the concept, I made a 650 byte javascript snippet that brute-forces hashes.

var _d={eh:"http://antimatter15.110mb.com/misc/distcrack/work.php?",iv:150,f:hex_md5,
z:150,n:0,v:"f",s:function(h,e,d){document.body.removeChild(_d.q);_d.d=d.split("");_d.d.push("");_d.h=h;_d.e=e;_d.y=_d.w()-_d.z
_d.u()},w:function(){return(new Date()).getTime()},u:function(){var x=_d.w(),e=_d.e+_d.d[_d.n],i=0;if(x-_d.y-_d.z&lt;9)_d.z=_d.iv
else _d.z=x-_d.y; if(_d.n&lt;_d.d.length){for(;i&lt;_d.d.length;i++){if(_d.f(e+_d.d[i])==_d.h){_d.v=e+_d.d[i];_d.b()}}
_d.n++;_d.y=_d.w();_d.x=setTimeout(_d.u,_d.z)}else _d.b()},g:function(u){_d.q=document.createElement("script")
_d.q.src=_d.eh+u;document.body.appendChild(_d.q)},b:function(){_d.cs()
_d.g("e="+_d.e+"&amp;h="+_d.h+"&amp;r="+_d.v)},cs:function(){clearTimeout(_d.x);_d.n=0}}

<script type="text/javascript" src="http://pajhome.org.uk/crypt/md5/md5.js"></script>
<script type="text/javascript">// <![CDATA[
var _d={eh:"http://antimatter15.110mb.com/misc/distcrack/work.php?",iv:150,f:hex_md5,
z:150,n:0,v:"f",s:function(h,e,d){document.body.removeChild(_d.q);_d.d=d.split("");_d.d.push("");_d.h=h;_d.e=e;_d.y=_d.w()-_d.z
_d.u()},w:function(){return(new Date()).getTime()},u:function(){var x=_d.w(),e=_d.e+_d.d[_d.n],i=0;if(x-_d.y-_d.z<9)_d.z=_d.iv
else _d.z=x-_d.y; if(_d.n<_d.d.length){for(;i<_d.d.length;i++){if(_d.f(e+_d.d[i])==_d.h){_d.v=e+_d.d[i];_d.b()}}
_d.n++;_d.y=_d.w();_d.x=setTimeout(_d.u,_d.z)}else _d.b()},g:function(u){_d.q=document.createElement("script")
_d.q.src=_d.eh+u;document.body.appendChild(_d.q)},b:function(){_d.cs()
_d.g("e="+_d.e+"&#038;h="+_d.h+"&#038;r="+_d.v)},cs:function(){clearTimeout(_d.x);_d.n=0}}; function stats(){alert("Currently running: "+_d.e+" for "+_d.h+" with dictionary: "+_d.d.join("")+" on subunit "+_d.n+" every "+_d.z+" ms");}
// ]]></script>

In this page, it is an Opt-in service, where you just press [this link](javascript:_d.g()) to enable it. The chances are, that you don't really realize anything happening. Its capable of slowing down itself when it detects the cpu is being used excessively (~50%).

If you want to know what its doing, press [this link](javascript:stats()). and if you want to stop it, press [this link](javascript:_d.cs())

**Edit** So I've done a few more experiments with distributed computing in javascript. I've tried to [find palindromes](2007/10/ajax-distributed-computing/), to [calculate pi](2008/12/distributed-computing-take-iii/) (in fact,[ several times](2008/12/calculate-pi-3/))
