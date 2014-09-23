---
title: Ajax Animator Thoughts
author: admin
date: 2008-10-25 11:10:58
tags: 
  - collaboration
  - GAE
  - goals
  - internet exploder
  - online
  - privacy
  - rewrite
  - roadmap
  - versions
template: article.jade
---

I've set some tiny goals for Ajax Animator 0.21/0.22/0.23/0.24/0.25\. I'm not really good with version numbers.

0.21 is mostly to work on the collaborative, online, web 2.0 aspect of it. Enabling collaboration is important, and I'm a huge supporter of User Created content (virtually all my projects are open source, and they include some entirely user-created things like my MMORPG, Project Wikify, and a few others). At one point, since the old ajax animator (not anymore) would keep logs of everything previewed (as we needed to convert it to flash to preview). I would enjoy people trying out how things were like. That was in the day where there were to tools: rectangles and sticks, and the lines didn't tween well. Color picking was unnecessarily complicated, the tweening engine crashed every minute, and couldn't do anything, etc. Since the 0.2 rewrite, things are much better, but I still miss having those user-management features.

If you didn't know that, User Management/Sharing has been in the ajax animator for a while. It was frequently added, removed, mutilated, upgraded, etc. I think it was there since the DHTML Goodies days (0.08?). It got removed for a while, got added again, removed, rewritten, and now removed again. I look forward to adding it again.

I guess much of it is already there. The login should look pretty much the same as the old one, but with the whole login thing replaced with a single OpenID box and a login button. I'm not exactly sure what to do after this. I think there should be a little profile box that replaces the login panel. I'm debating whether the profile should house a list of your saved animations, or if it should be nested into that Animation browser (that actually works!). I'm leaning towards the latter. The profile may house a link to your folder in the animation directory, a button to save your edits (as with File-&gt;Save-&gt;Webserver). Etc.

With that, it would include some form of user management system. I've almost completely settled on OpenID because of it's flexibility, futuristicity, freaking-awesomeness (getting a bit overboard...). I've just been surfing the web (Wikipedia stuff) and I'm increasingly interested in OpenID, as it seems much more "ajax-friendly" than I previously thought.

Some time, i'd like to switch to a more scalable app-engine oriented system (it's already serving up static JS now). I'll use my server at antimatter15.com more (Java-Enabled), so there can finally be decent flash export :)

One thing that i'd really like, that's really probably painful, is to better support IE. There's no problem with IE support in the general components of the Ajax Animator (Tweening/UI/Save/Format/Abstraction Layer/etc), but rendering isn't very good. I'd like for it to be better. OnlyPaths is already great, but IE support is big for it to become mainstream. I'd like it for use in a more educational and amature(ish) setting, where people have the most use for free/opensource/easy-to-run apps. In education, many people are still using IE, and that's a big problem.

I've been looking into other renderers for the future of the Ajax Animator to run on. For the forseeable future, the editor will be OnlyPaths, because it is the only one that really fits the needs of the project. But it's built on a less-clean, prototype-like (non-namespaced) foundation, and isn't built exactly as it should. It's not up to me, but I think that OnlyPaths should be an editor, rather than a renderer, or at least the renderer and the editor to have very visible lines between. Right now, much of the editor interface is in the renderer. That means a lot of unnecesary work. The addTracker function is currently in the renderer, this is completely the wrong thing. It was fine in the days when it was Richdraw and the tracker was just a blue square, but that's not scalable. On this trend, you would need 2 copies of essentially the same code (VML/SVG) for the tracker/etc. I'd much prefer to have a interactive-less renderer and addTracker function in the editor, where all the actions are calls to the drawing API. Either Onlypaths has to get a better VML renderer, or we have to switch rendering engines to something like Dojo.GFX or Raphael and port the editor over to the new renderers. I like the current OnlyPaths one a lot. It's been developed side-by-side with the Ajax Animator, and is very well integrated. I dont like Dojo.GFX too much, because it's dojo-dependencies, but it's a very solid and stable framework. And Raphael isn't as powerful as the current OnlyPaths engine yet.
