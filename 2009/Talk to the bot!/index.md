---
title: Talk to the bot!
author: admin
date: 2009-09-02 1:28:42
categories:
  - Omeglebot
tags:

template: article.jade
---

[http://botbash.antimatter15.com/chat.htm](http://botbash.antimatter15.com/chat.htm)

You can talk to the awesome omegle-learning robot with it's 20MB database!

The way it works is pretty cool, there is that client which is using postMessage to communicate to a frame hosted with google app engine which is polled at an insanely fast rate (practical DDoS at 2 requests per second). That gets stored on a datastore, and my server in my basement is also DDoSing google, recieving new messages (probably using BOSH/XMPP would be better...). It uses JSONP to query the server's php server and computes a response with MySQL and PHP. Then it's sent to the HTML, postMessaged to the iframe and t hen ddoses google and etc.
