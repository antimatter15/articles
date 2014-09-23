---
title: zQuery
author: admin
date: 2010-09-06 8:45:15
tags: 

template: article.jade
---

The name comes from the fact that of letters which can prefix the word "Query", the letter z appears to have the least results, and its avoidance of resemblance to jQuery to some extent really underlies what it is: (yet another) lightweight jQuery clone.

This project uses defineGetter/Object.defineProperty to make a jQuery-style (but more like the DOM) API in under 1k (minified).

Example:

$('#magic a').className += ' link';
$('body').find('a').innerHTML
$('body').textContent += 'blah' //works on firefox too!

BTW:
This library is totally untested
