---
title: How I Would Design The Browser 2 Addons
author: admin
date: 2009-08-21 4:37:55
tags: 
  - addons
  - browser
  - chrome os
  - google
  - idea
  - jetpack
  - prodigy
template: article.jade
---

So I was watching Aza Raskin's TechTalk on [Jetpack](http://www.youtube.com/watch?v=Wp5Crg_KI10&amp;feature=sdig&amp;et=1250769392.47), and I was thinking on how I would design an extension system. I would have to say to not have one, it's just too complex, and why restrict the sound recording functionality to a taskbar. Even worse, why fragment the API and require someone to use Flash or &lt;audio&gt; in the page space and have a nice jetpack.future.import("audio") for a taskbar?

I think a good idea would to expose the power to web pages. The page could request special capabilities through a magical button dropdown or bouncy annoying notifier on a corner of the page saying permissions, populated by checkboxes of whatever features that the page wants to be able to use.

I think bookmarklets are almost perfect. Adding some more greasemonkey-like features would make it just about perfect. Scripts can run with the same permissions as the page, and the page's permissions can be granted easily by the user (and the permissions persist through refreshes and browser restarts). Again, if functionality is not supported, things can gracefully degrade with partial functionality.

After that, is the idea of background tabs or alternatively, merging the statusbar type widgets into the tab bar. This is logical with everything merged into the page, and allows things to gracefully degrade if they don't support the feature. You also get the benefits of being able to reorder remove, get info (which would be the contents of an extension page), etc. I think the interface for a plugin that operates in the background (like a gmail notifier) would be just a small tab that only has an icon, with special flag that makes it run on browser start (I think this could be one of the things for the permissions panel).

So one problem I see in the way Jetpack works, is that it doesn't easily allow you to make a jetpack that hacks another running jetpack. Sure you can "fork" it, but that defeats the purpose of extensions, rather than having extensions only 1-level deep, make it work all the way down. The easy way I see is just to use the bookmarklet philosophy, and everything can mess around with anything within the page. So if you have a GMail notifier, that came out before the tab persist feature existed, you could just add a simple bookmarklet-type-greasemonkey thing that adds something to the permissions box that says "Persist Page" and then the user could check that in order to make a background GMail Notifier that runs on browser startup.

Malware is easy to fight now. Imagine if every application was forced to have a icon in the taskbar of windows at all times. Finding malware is as easy as looking for things you dont want running and closing it. And if some tab-bar autohide is to be implemented on the system, only people who are quite experienced would use 10+ extension/notifier pages and it would still be easier to recognize than finding some other strange wcultns.exe or whatever when half of the system things look like that.

With these features, Browser as an OS would really make sense. I wouldn't be suprised if Google Chrome OS implements some stuff that are similar to what I've listed here.
