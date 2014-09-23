---
title: Firebug Console Error Stack
author: admin
date: 2009-11-01 3:34:01
tags: 

template: article.jade
---

I noticed that unlike errors thrown otherwise in the page, when there is an error executing something in the console, you get an error with a link to an object on the DOM browser and have to parse a non-line-delimited mess of the error object instead of the nice looking stuff in the console saying line numbers.

To get around that and have the nice parsed out pretty error messages, wrap the code in the console with try{/*code here*/}catch(e){console.error(e)} though I hope that its just a tiny issue that they will eventually resolve in a later version
