---
title: vX Ajax is almost 10 bytes smaller
author: admin
date: 2008-12-04 6:15:06
categories:
  - vX JS
tags: 
  - ajax
  - smaller
  - vX JS
template: article.jade
---

Okay, so 0 = false, so it makes sense that !0 = true. but also 1 = true, so that saved 1 byte.

Since there's no .readyState attribute > 4, instead of .readyState == 4, you can do .readyState>3

the big one was ActiveX, which was originally

	x=new(this.ActiveXObject?ActiveXObject:XMLHttpRequest)('Microsoft.XMLHTTP')

I noticed how this.activeXObject was repeated unnecessarily. So i added a new variable y

	y=this.ActiveXObject

then I did:

	y=this.ActiveXObject;x=new(y?y:XMLHttpRequest)('Microsoft.XMLHTTP')

thanks to dynamic languages, I could use x, and just reset it to something else (saving a variable declaration!)

	x=this.ActiveXObject;x=new(x?x:XMLHttpRequest)('Microsoft.XMLHTTP')

Now I just need to find a way to shrink 
	
	x.setRequestHeader('Content-type','application/x-www-form-urlencoded')
