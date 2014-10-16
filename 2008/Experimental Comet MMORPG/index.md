---
title: Experimental Comet MMORPG
author: admin
date: 2008-05-02 7:19:38
categories:
  - CometRPG
  - Games
tags: 
  - ajax
  - character
  - code
  - comet
  - complex
  - ExtJS
  - firebug
  - firefox
  - game
  - games
  - internet explorer
  - long polling
  - mmorpg
  - password
  - php
  - real time
  - sprites
  - untitled
  - url
  - xhr poll
template: article.jade
---

Note: This is likely the first AND last release Ever. I'm gonna go on working on Ax v0.2 after this is finished (tomorrow)

I think its finally *ready* for showing people (still proprietary though :P). It is coded using Ajax/Long-Polling Comet, which as far as I'm concerned, is the first of it's kind. It uses ExtJS for its user interface. it's page load is ~2mb in size, and there is a huge amount of static data handled. Its following how most my apps are made: using the most client side code possible. I donno why, but it just is.

Since it uses Comet technology (specifically, long-polling), the requests made are minimized, and supposedly much more scalable. Requests are *only* made when necessary, and due to Comet technology, it only updates when there is something to update.

Since most of the processing is done on the client side, the server only has to handle the static content.

An interesting, albeit geeky feature, is a sort of command-line functionality. I attempted to build the entire system (somewhat like a Unix system) where most if not everything graphical is backed by a set of commands. Well, the real-time chatbox (which again, uses comet to reduce load on servers) detects if the input starts with the &gt; character. if it does, then it parses it as a set of commands. Its relatively smart, so if you type in a global variable name, i'll give you a JSON dump of the contents, and if its a function, i'll call it, and if it is an expression then it'll eval it.

There is no such plotline yet. Just random stuff that pops in my head (read: iWorld) and etc. there is also no title yet. (named: "Untitled"). Part of the game itself, is to build the game, using its built-in pixel-sprite-graphics editor.

Currently, it is restricted to modern browsers only. Firefox being my development platform (duh. what kind of js developer doesn't use firefox/firebug? but i heard the IE8 dev toolbar is good cause its a clone of firebug..) will obviously work best. IE may or may not work. though platform agnosticism was one of the design goals. Opera/Safari is likely, but i'm not certain. most mobile browsers will fail (i tried apple iphone safari support, but it is weird around ExtJS)

It has some features, such as a relatively nice UI (well... nice compared to the *others*).  Session saving, worlds, sprite/npc authoring, Character IDE, npc battles, pvp, store, panning, prelimary quests,  items, friends, magic/abilities, a CLI, some crappy code, moderation, adminstration, etc.

Oh, and the password is "password" in case you wanna make new sprites.  The URL is http://cometrpg.110mb.com/
