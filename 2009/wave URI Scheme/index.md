---
title: wave URI Scheme
author: admin
date: 2009-10-10 3:50:32
categories:
  - Google Wave
tags: 

template: article.jade
---

One of my major gripes against Wave is that there is no good way to link. If you copy and paste the URL, it never autolinks, and if it does, then it totally epic fails in the process for most content systems. The URLs are insanely long, and totally ignores the federated nature. If you want a federated _protocol_ you shouldn't do links by copy and pasting client URLs.

Similar to the mailto: protocol used in HTML. I think a wave: protocol would be far more suitable. HTML5 has this feature called navigator.registerProtocolHandler which while part of the recommendation, is only implemented by Firefox 3.0+

How awesome is this new linking system? Well, the great thing is that Extracting the URL is totally easy:

https://wave.google.com/wave/#restored:search:with%253Apublic,restored:**wave:googlewave.com!w%252BAf00O-Y67**

That's the URL, copy and paste it to a browser and it will open in google wave (well the software can be configured to open up in any wave client which is why this is so important)! You get to totally get rid of all the stuff before that makes it specific to the Google Wave client.

[Link to the wave discussion of this](wave:googlewave.com!w%252BAf00O-Y67) yes and obviously the link is linked using MY protocol handler.

Well, browsers don't come out of the box with support for the wave: protocol, so how do I get it to work? Well, there are a few issues that make it harder.

*   Wave IDs are double-escaped
*   %s auto escapes
*   registerProtocolHandler only registers URls for sites for their own site (antimatter15.com can not register wave: handler for wave.google.com)
*   Inconsistency with using the unescaped, or single escaped or double escaped wave IDs
So first I tried hacking it together with jsbin, but it gave errors. After re-reading documentation on mozilla's devwiki. I tried making a bookmarklet. After that made issues with esaping, I started making a redirect server for it.

So the now working thing is here: [http://antimatter15.com/misc/wave/uri/install.htm](http://antimatter15.com/misc/wave/uri/install.htm)

It still has linkability issues because nobody can rely on the autolinking scripts as they all probably ban the wave: protocol (and with many sites, manual linking would also be banned).
