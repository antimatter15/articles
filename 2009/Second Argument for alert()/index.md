---
title: Second Argument for alert()
author: admin
date: 2009-09-02 8:41:54
categories:
  - Design
  - Web Notifications
tags: 

template: article.jade
---

**I was actually writing this a while ago and was holding it off until I made some firefox extension or something that implemented this but interestingly Google just made a Notifications API for Chrome, which is pretty cool, and I think it could be part of something in ChromeOS or Gears which will be somewhat similar to my post on how I would design a Browser Addon System. And while Google's one doesn't (as far as i can tell) have a public API, I think it would be nice to have it implemented as a second argument for alert()**

Alert is old, annoying and locks your app. It is a tragedy that the web has no better, preferably asynchronous notification system outside of built-in browser APIs.
And if all browsers implemented this then the world would be a happier place with less alerts. People could enable richer web apps like mail or IM to provide status and message updates. Notified addons could be made cross browser and way simpler ad just web pages (maybe keep them all ad iframes on the start page).
