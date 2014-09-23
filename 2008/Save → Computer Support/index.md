---
title: Save → Computer Support
author: admin
date: 2008-07-10 9:02:56
tags: 

template: article.jade
---

No time, copied from SVN commit message:
> Working Menu-&gt;File-&gt;Save-&gt;To Computer button. Does ajax request to save_proxy.php (new file) and if the request fails to output the correct stuff, it falls back to the local client based dataURI method (btw, won't work on IE).> 
> 
> BTW. this has been here for a few revisions already, but those grey boxes that fall from the sky, well, you can click on them to close them. nifty feature eh?
It currently will fail and definitively will fall back to the dataURI method now because I haven't installed the new save_proxy.php on the testing server. Will do that tomorrrow, I dont have time now.
