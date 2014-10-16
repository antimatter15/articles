---
title: HTTP based federated protocol for real time hierarchical message manipulation
author: admin
date: 2010-08-29 1:53:04
categories:
  - Google Wave
tags: 
  - awesomeness
  - better than wave
  - github
  - google wave
  - http
  - long title
  - messages
  - node.js
  - server
  - the medium is the message
  - youtube
template: article.jade
---

<object style="height: 344px; width: 425px;" classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" width="100" height="100" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,40,0"><param name="allowFullScreen" value="true" /><param name="allowScriptAccess" value="always" /><param name="src" value="http://www.youtube.com/v/uJvkUvMALM8?version=3" /><param name="allowfullscreen" value="true" /><embed style="height: 344px; width: 425px;" type="application/x-shockwave-flash" width="100" height="100" src="http://www.youtube.com/v/uJvkUvMALM8?version=3" allowscriptaccess="always" allowfullscreen="true"></embed></object>

In other words. It's[ like google wave](http://googleblog.blogspot.com/2010/08/update-on-google-wave.html), but simpler in every possible way.

This protocol uses two servers. The federation server and the storage server. The latter is incredably simple. In fact, the reference implementation is only about 200 lines of JS (Node.JS FTW). Thats because a storage server accomplishes just about three things. It receives message deltas. It applies them. And it pushes the delta to all subscribers. The subscribers are the federation servers, they act on the behalf of multiple clients, keeping track of users, their inboxes, etc.

Anyway, the big part about the design is that there is only one unit of information, and that is the message. There's no such thing as waves, wavelets, conversations, private replies, threads (sort of lying here), blips and other information. It's just messages. Messages are stored on storage servers, and are filled with HTML and a tree of information.

Messages can have other messages inside them. It's just some xml-ish stuff. &lt;thread&gt;&lt;/thread&gt; is a thread and &lt;message name="http://blahblahblah.com/blahblahblah"&gt;&lt;/message&gt; is a message that goes inside the thread. You can stick it anywhere. In the middle (inline replies!) or at the end (normal replies!).

Messages don't even have to have text. Gadgets are just messages that are slightly different.

[http://github.com/antimatter15/awesomeness](http://github.com/antimatter15/awesomeness)

There's a lot that it doesn't do because I'm too lazy to do it. And I can't give you a live demo because I don't have a node-enabled server.
