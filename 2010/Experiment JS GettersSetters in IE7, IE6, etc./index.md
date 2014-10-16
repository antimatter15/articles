---
title: Experiment JS Getters/Setters in IE7, IE6, etc.
author: admin
date: 2010-02-20 8:44:37
categories:
  - Uncategorized
tags: 

template: article.jade
---

Getters and Setters in JS have been plagued with a few issues. Firstly, IE didn't support it until IE8 and IE8's implementation follows the Ecmascript Object.defineProperty spec rather than the de-facto standard of __defineGetter__/__defineSetter__. It's pretty much trivial to make a Object.defineProperty function which writes to __defineGetter__/__defineSetter__. Here is something quite a bit more interesting: Adding getters and setters support to (theoretically) any browser, and I don't see why versions of Netscape and IE5.5 and all the other ancient browsers couldn't be made to work. All without following the hideous java-esq getBlah() and setBlah() paradigm.

Instead, my solution is pretty simple.
`
getset(function (){
var cheesecake = {}
  Object.defineProperty(cheesecake, "description", {
    get : function () {
      return this.desc + " and stuff added because of the awesome getter";
    },
    set : function (val) {
      this.desc = val + " stuff added for setter ";
    }
  });
  cheesecake.description = "Absolutely delicious";
  alert(cheesecake.description);
})
`

The awesomeness is pretty intense, you might have to look at a while for the awesomeness to sink in. And if you still don't get awe-strucked by the amazingness, think again **getters and setters consistently in all browers, even the ancient ones**. The code is using getters and setters, no syntactic hacks are apparent. The only deviation is a little getset(function(){}) which wraps around the code.

First thing the library does, is it defines Object.defineProperty if its not already defined. It checks for __defineGetter__ support and uses that if possible. If it's not defined (this is the routine for ancient browsers like IE7 and below) it declares obj['__get_'+prop] = getter, etc. Still nothing special. If it stopped here, then you would access a getter by obj.__get_description() or obj.__set_description(text), even more hideous than Java.

The brilliance is in the getset function. Basically, it does the checks for __defineGetter__ and native defineProperty again, if its there, then it just executes the argument.

This time, if something is not defined, the function is decompiled. Basically fn.toString(). Yay, now is the code that is inside, now what? A hacked together super duper slow crappy and mostly non-functional regex based parser crawls through it and generates some hideous new markup:
`function (){
__getsethandler(cheesecake,'description',"Absolutely delicious")
;
alert(
__getsethandler(cheesecake,'description'/*__ID1__*/)
)
};`

And now __getsethandler goes on and does the obvious. And hopefully someone who knows how to fix the parser will and people will start using getters and setters.

For anyone willing to try it in a browser (I've only tested it under Chromium Nightly, Opera 10, Firefox 3.5 and IE 7 under Wine). Even better would be if someone is willing to fix up the parser thing. [http://jsbin.com/oriqo/15](http://jsbin.com/oriqo/15)

Please comment if you find a browser which it doesn't work on of you fix the parser. It may be possible to hook it onto Narcissus (though ironically, I think Narcissus uses getters and setters...) or JSReg instead of writing a parser from scratch.
