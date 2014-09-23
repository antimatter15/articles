---
title: vX Ajax is almost 10 bytes smaller
author: admin
date: 2008-12-04 6:15:06
tags: 
  - ajax
  - smaller
  - vX JS
template: article.jade
---

Okay, so 0 = false, so it makes sense that !0 = true. but also 1 = true, so that saved 1 byte.

Since there's no .readyState attribute &gt; 4, instead of .readyState == 4, you can do .readyState&gt;3

the big one was ActiveX, which was originally

<tt>x=new(</tt><tt>this.ActiveXObject</tt><tt>?</tt><tt>ActiveXObject</tt><tt>:XMLHttpRequest)('Microsoft.XMLHTTP')</tt>

I noticed how this.activeXObject was repeated unnecessarily. So i added a new variable y

<tt>y=this.ActiveXObject</tt>

then I did:

<tt>y=this.ActiveXObject;x=new(y?y:XMLHttpRequest)('Microsoft.XMLHTTP')</tt>

thanks to dynamic languages, I could use x, and just reset it to something else (saving a variable declaration!)

<tt>x=this.ActiveXObject;x=new(x?x:XMLHttpRequest)('Microsoft.XMLHTTP')
</tt>
Now I just need to find a way to shrink <tt>x.setRequestHeader('Content-type','application/x-www-form-urlencoded')</tt>
