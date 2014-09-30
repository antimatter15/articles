---
title: XPath Bookmark Bookmarklet
author: admin
date: 2009-11-01 4:33:48
tags: 
  - bookmarklet
  - elitist
  - future
  - hack
  - html
  - link
  - userscript
  - visionary
  - web
  - xpath
template: article.jade
---

    javascript:(function(){
      //inspired by http://userscripts.org/scripts/show/8924
      var s = document.createElement('script');
      s.setAttribute('src','http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.js');
      if(typeof jQuery=='undefined') document.getElementsByTagName('head')[0].appendChild(s);
      (function() {
        if(typeof jQuery=='undefined') setTimeout(arguments.callee, 100)
        else{
          jQuery("*").one("click",function(event){
            //http://snippets.dzone.com/posts/show/4349
            for(var path = '', elt = jQuery(this)[0]; elt && elt.nodeType==1; elt=elt.parentNode){
              var idx = jQuery(elt.parentNode).children(elt.tagName).index(elt)+1;
              idx>1 ? (idx='['+idx+']') : (idx='');
              path='/'+elt.tagName.toLowerCase()+idx+path;
            }
            window.location.hash = "#xpath:"+path
            event.stopImmediatePropagation()
          })
        }
      })();
    })()

Sometimes you want to link to a certain part of a web page. That's great and works well if its a nice site that clearly defines anchor tags to link to, but what if there isn't?

Today I just remembered something and I thought that I saw something earlier with a xpath URL hash. I googled it and couldn't find anything native to the browser (please correct me if I'm wrong) but found this script: [http://userscripts.org/scripts/show/8924](http://userscripts.org/scripts/show/8924) which is basically what I was thinking about. But it was allegedly hard to make those URLs, so I thought why not make a bookmarklet to make linking to those URLs simple? So I quickly hacked this together

    javascript:(function(){var a=document.createElement("script");a.setAttribute("src","http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.js");if(typeof jQuery=="undefined"){document.getElementsByTagName("head")[0].appendChild(a)}(function(){if(typeof jQuery=="undefined"){setTimeout(arguments.callee,100)}else{jQuery("*").one("click",function(d){jQuery(this)[0].scrollIntoView();for(var e="",c=jQuery(this)[0];c&amp;&amp;c.nodeType==1;c=c.parentNode){var b=jQuery(c.parentNode).children(c.tagName).index(c)+1;b>1?(b="["+b+"]"):(b="");e="/"+c.tagName.toLowerCase()+b+e}window.location.hash="#xpath:"+e;d.preventDefault();d.stopPropagation();jQuery("*").unbind("click",arguments.callee)})}})()})(); 

(Just drag it over to your bookmarks bar as with any other bookmarklet). To use, just click on the bookmark, and click on the element you want to link to. You should see the URL will update with a xpath hash showing you the copy-pastable link to that element. The code is quite simple and should work on Firefox, Chrome and all the other browsers (maybe even IE) but the ability to auto-scroll and actually use the links is only available to Firefox and potentially Opera and Chrome.

And I'm working on a Chrome Extension for the original userscript (which should work with Chrome's userscript support, but I'm going to try packaging it as a chrome extension file) But sadly chromium for linux isnt up to speed especially with extension development.

The source can be found [http://gist.github.com/223708](http://gist.github.com/223708).

**_Update:_<span style="font-weight: normal;"> _Fixed the link for the path and added some stuff. <strong>Update 2**__: Fixed bookmarklet, now scrolls to clicked, executes only once, prevents default_</span></strong>
