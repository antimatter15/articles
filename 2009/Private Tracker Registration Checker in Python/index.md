---
title: Private Tracker Registration Checker in Python
author: admin
date: 2009-07-31 1:33:51
categories:
  - BitTorrent
tags:
  - appengine
  - GAE
  - private tracker
  - python
  - torrents
  - xmpp
template: article.jade
---

Well, I wanted a demonoid account for no apparent reason. So I wanted to search for private trackers, and found this app called [Tracker Checker 2](http://www.stamcar.com/2007/07/25/tracker-checker-2-public-preview/) It's great and all, but it doesn't work well on linux. Or at least for me, I run it and it pops up a window for a few milliseconds and then closes. There's nothing in the tray but the process looks like it's still running. So I looked at the trackers.xml file and thought it would be easy to create another one.

So I quickly hacked together a python script that parsed the xml file and checked for trackers. For some reason, Demonoid said it was open while it was actually closed, so I made a little extension to the format.

I'm actually probably not gonna use this, but I've made this private tracker registration checker app in python. It uses a trackers.xml file that is compatable with the [Tracker Checker 2](http://www.stamcar.com/2007/07/25/tracker-checker-2-public-preview/) app. It supports a slight extension to the protocol by being able to check if a certain phrase is _not_ in a page. It's multithreaded and uses expat for xml parsing and urllib2 to download the pages.

I think it would be pretty cool to integrate it with XMPP and port it to Google App Engine, and send out alerts to people when trackers are open.

It has no UI, it's just a little command line app that could be used as a cron job and integrated with XMPP.

[Download here](http://antimatter15.com/misc/trackerchecker.tar.gz)
