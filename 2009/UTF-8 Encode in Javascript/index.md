---
title: UTF-8 Encode in Javascript
author: admin
date: 2009-09-02 8:39:09
tags: 

template: article.jade
---

UTF-8 encode for Javascript. I'm not going to attach a license to it, maybe Public Domain or something, it's slightly more lightweight than the other implementations.

	"utf8": function(input) {
		//return unescape(encodeURIComponent(input)); //may or may not work
		for(var n = 0, output = ''; n < input.length; n++){
			var c = input.charCodeAt(n);
			if(c &lt; 128){ 	      
				output += input[n]; 	    
			}else if(c &gt; 127) {
				if(c &lt; 2048){ 	        
					output += String.fromCharCode(c >> 6 | 192);
				}else{
					output += String.fromCharCode(c >> 12 | 224) + String.fromCharCode(c >> 6 & 63 | 128);
				}
				output += String.fromCharCode(c &amp; 63 | 128);
			}
		}
		return output;
	},
