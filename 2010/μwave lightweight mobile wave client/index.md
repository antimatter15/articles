---
title: μwave lightweight mobile wave client
author: admin
date: 2010-05-29 10:08:40
tags: 
  - google
  - google wave
  - project
  - screenshot
  - update
  - wave reader
template: article.jade
---

[![](http-micro-wave.appspot.com-static-ui.html-Chromium_025.png "Microwave Wave-View May 29")](http-micro-wave.appspot.com-static-ui.html-Chromium_025.png)[![](http-micro-wave.appspot.com-static-ui.html-Chromium_023.png "Microwave Search-View May 29")](http-micro-wave.appspot.com-static-ui.html-Chromium_023.png)

I like bragging when I do something nobody else has done before. And **μwave **is the first true third-party wave client which is compatible with Google Wave. It's free to use at [http://micro-wave.appspot.com/](http://micro-wave.appspot.com/) and works great on mobile devices. It supports searching for waves, opening them and writing replies.

Currently it doesn't know read/unread state of the waves from the search panel and doesn't know read/unread blips, but as of time of writing, its a limitation and flaw in the current version of the **Google Wave Data API **(introduced just ten days ago at Google I/O). Expect this to be resolved in the near future with upcoming versions of the API and this application.

The source code for the server component is open-source and can be [found on github](http://gist.github.com/417035) (though it's slightly outdated, but the important stuff is there). It's fairly simple (It's based on the original [example code](http://oauth.googlecode.com/svn/code/python/oauth/example/client.py) so I'm going to have the same MIT license), but one of the few python scripts which can do authentication with google and pass commands to the data api.  It relies on the [Python OAuth Library](http://oauth.googlecode.com/svn/code/python/oauth/).

The Blip renderer component of this is licensed under the MIT license and can be found on the [old microwave repo](http://microwave.googlecode.com/hg/bliprender2.html). The only part left is the interface, which is going to be the usual GPLv3.

For a little bit of history, this isn't exactly a new project. The[ google code project](http://code.google.com/p/microwave/source/detail?r=cb27d32b3a5ee5aeaef38c58463268e7931f60f0) has existed since January 9th, 2010\. The purpose was to create a mobile-friendly version of Wave Reader. But that goes even deeper, I can trace it back to the[ original Static-Bot](http://static-bot.appspot.com/view/?id=googlewave.com!w+DUX6159GV) dated to October 18, 2009\. Then, the Google Wave embed API allowed people to view waves only if someone had a Google Wave account and was logged in at the time. This was quite problematic as Wave was still a limited preview which not many people had and probably hampered adoption.

Another separate but eventually convergent issue which led to the microwave project was "[Desktop Wave Reader + GWave Client/Server Protocol](http://antimatter15.com/misc/read/?googlewave.com!w+Ze3l0mj0A)" post which I made on October 29th of 2009.

During late October of last year, I reverse-engineered some of the features of the Google Wave client. Up until then, the only published specs were the federation protocols, which dealt with how multiple wave servers would use a common protocol to allow multiple users without a central authority and for the gadget and robot apis. Notably missing was a client/server api, for a user of specifically the google wave client, which did not yet support federation (and to date, preview still does not), and to browse/view the waves in one's inbox without needing to switch to an entirely new provider. The first component was the ability to read waves. After that was accomplished, I tried to reverse engineer a more complex aspect of the protocol, which was the ability to search waves. I eventually realized that that component, search was part of a larger puzzle, which was the real-time BrowserChannel wire protocol which virtually all of wave was based. I made some progress, but near the end, I gave up in frustration. Luckily, someone else became interested in the same thing, and[ Silicon Dragon basically got search working](github.com/waverz/waveclient).

This happened now in early December. I started on a project called [Wave Reader](2010/01/wave-reader-4-6/), which merged the ideas of static-bot with the desktop wave reader and a new functional blip rendering engine. At that time, the Google Wave client was still horrendously slow, taking several minutes at times to load large waves.

On January, I began a project to merge Wave Reader and the wire protocol (search). I thought an awesome name would be microwave (or μwave) and started the code repo on January 9th. I worked on it a bit, so that it was mostly complete, with search and loading all working, with one missing component: login. Eventually, I got bored and the project lay abandoned for a few months.

This gets us to basically 4 days ago, when I started working on a renaissance of the μwave project, based on the recently released Google Wave Data API. The first component was creating a new blip renderer specifically designed for parsing the new (much cleaner) json format which is part of the robots api. Then I created a client around that and created a python backend for having it work on app engine.

The Future is always awesome to prophesize about. In the coming weeks or days, google will probably update the data api to allow for information like  So, while http://micro-wave.appspot.com will likely remain free and maintained for the forseeable future, I do plan on making a paid iPhone/iPad app. The iPhone app may have some extra features like offline/caching support.
