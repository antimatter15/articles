---
title: Experiment Ruby-style function auto-calling in Javascript
author: admin
date: 2010-07-22 1:21:26
tags: 
  - automatic calling
  - function
  - ruby
template: article.jade
---

I have no clue what it's called when ruby automatically runs a function.
After not totally understanding [def.js](http://github.com/tobeytailor/def.js) and looking at this [coffee-script issu](http://github.com/jashkenas/coffee-script/issues/514)e from the [cappuccino github issues browser](http://githubissues.heroku.com/#jashkenas/coffee-script/514). I had a horrible idea.
	
	Function.prototype.valueOf = function(){return this()}


What does it do?

	function getValue(){
		return 42
	}
	if(getValue == 42){
		alert('fortytwo')
	}else{
		alert('not fortytwo')
	}

Notice notably absent in the if statement are the expected parentheses '()' needed to call them. It gets stranger still.

	alert(getValue == 42); //true
	alert(getValue() == 42); //true
	alert(getValue() === 42); //true
	alert(getValue === 42); //false
	typeof getValue() //number
	typeof getValue //function

	var sample1 = getValue;
	typeof(sample1) //function

	var sample2 = getValue();
	typeof(sample2) //number

One advantage is that it makes a super hacky/semi-working implementation of getters that _should_ work universally (maybe). Except that it doesn't. It's practically useless.
