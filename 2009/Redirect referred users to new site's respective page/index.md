---
title: Redirect referred users to new site's respective page
author: admin
date: 2009-07-14 1:09:28
categories:
  - Meta
tags: 
  - hosting
  - wordpress
template: article.jade
---

So as you may know, I have moved to a new host and I need to move all things over so I made this awesome script that I hacked together to redirect all users visiting the old site to the new site and the respective page as long as they are being referred from a third party.

It's pretty short and goes at the top of index.php. Probably won't be useful to anyone but whatever :)

	if(isset($_SERVER['HTTP_REFERER']) && strpos($_SERVER['HTTP_REFERER'],"antimatter15") === FALSE){
	  header( "HTTP/1.1 301 Moved Permanently" ); 
	  header("Location: ?".$_SERVER['QUERY_STRING']);
	  die();
	}
