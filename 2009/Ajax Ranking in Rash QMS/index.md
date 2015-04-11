---
title: Ajax Ranking in Rash QMS
author: admin
date: 2009-06-20 3:10:04
categories:
  - Omeglebot
tags:
  - ajax
  - bash
  - rash
  - vX JS
template: article.jade
---

So i had this little project involving a quote repository and due to some trouble installing the superior Chirpy system, I used RQMS and did a few changes to add features like ajax ranking so you don't have to reload to rank something.

It only involved changing less than 10 lines and pasting a snippet of my vX Ajax library.

Replace lines 151, 152 and 153 with the following lines (respectively) in rash_output.php (the template).

	<a href="?ratingplus<?=$GET_SEPARATOR_HTML?>id=<?=$row['id']?>" onclick="plus(<?=$row['id']?>);return false" class="quote_ratingplus">+</a>
	(<span id="rating<?=$row['id']?>"><?=$row['rating']?></span>)
	<a href="?ratingminus<?=$GET_SEPARATOR_HTML?>id=<?=$row['id']?>" onclick="minus(<?=$row['id']?>);return false" class="quote_ratingminus">-</a>


Then add the following somewhere arbitrary in the <head> of rash_template.php

	<script type="text/javascript">
	var _=_?_:{}
	_.ajax=_.X=function(u,f,d,x){x=window.ActiveXObject;x=new(x?x:XMLHttpRequest)('Microsoft.XMLHTTP');x.open(d?'POST':'GET',u,1);x.setRequestHeader('Content-type','application/x-www-form-urlencoded');x.onreadystatechange=function(){x.readyState>3&amp;&amp;f?f(x.responseText,x):0};x.send(d)}
	_.id=_.G=function(e){return e.style?e:_.d.getElementById(e)}
	_.d=document

	function plus(ID){
		_.ajax("?ratingplus&amp;id="+ID, function(){
			_.G("rating"+ID).innerHTML = parseInt(_.G("rating"+ID).innerHTML)+1
		})
	}
	function minus(ID){
		_.ajax("?ratingminus&amp;id="+ID, function(){
			_.G("rating"+ID).innerHTML = parseInt(_.G("rating"+ID).innerHTML)-1
		})
	}
	</script>

I've packaged a sample rash template with the ajax functionality. You can get it here: http://drop.io/ajaxrash

And the purpose of this is of course for one of my new projects, BotBash a conversation repository between a little (really simple) bot i built and strangers on Omegle. You can see it in action on http://botbash.antimatter15.com
