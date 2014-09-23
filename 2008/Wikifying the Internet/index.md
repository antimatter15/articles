---
title: Wikifying the Internet
author: admin
date: 2008-08-29 1:24:21
tags: 
  - collaboration
  - parody
  - persistance
  - wikify
template: article.jade
---

What if you could edit a copy of any site in the entire web, and have it persist? Well, I'm working on a bookmarklet that basically does the classic (javascript:(function(){document.designMode="on"})()) but with persistance. It's going to store all changes to the web page on a centralized patch server (app engine?) and anyone who clicks on the bookmarklet will be instantly be able to see previous edits and make their own.

So, what could it be used for? Well, you could use it to fix small typos on the internet, Update far-outdated pages/info, and let's not forget, vandalize the home page of your arch nemisis. But as a wiki, everything can be reverted/etc. The design for the system is very nice, as it only stores the content modified by users, one way of averting legal action against me (i'll also be sure to add disclaimers too :)).

Of course the vandalism part will probably be what happens, as with most Wikis (besides the mother-of-all Wikis). it's still an interesting concept anyway. Maybe it'll make people happier, when every time they view their (usually empty) adsense page and always find it saying $100,000.00 for their day's earnings? And it's not forced on anyone, and if it becomes open-source (it's easily implementable anyway), the bookmarklets could be customized on custom servers, creating an endless amount of forks of the internet.

I only have a non-working prototype so far, i'm going to embark on a rewrite soon.  And thanks to the App Engine team for raising the limit to the number of apps-per-dev.

As you know, I'm sorta taking a break from the Ajax Animator. It's sometimes nicer to work on some smaller projects now and then.
