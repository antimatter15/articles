---
title: Why my Streamie fork is better than everyone else’s
author: admin
date: 2010-09-01 6:44:53
categories:
  - Streamie
tags: 
  - node
  - streamie
  - twitter
template: article.jade
---

So the [future is here and everyone is forking running websites](http://www.nonblocking.io/2010/08/future-is-here-i-just-forked-running.html). The rate of development is pretty insane and I've already disabled [Chromed Bird](https://chrome.google.com/extensions/detail/encaiiljifbdbjlphpgpiimidegddhic) and I'm switching to having Streamie as a pinned tab, which also leads inevitably to the question ["Why is a pinned application tab aesthetically different from a Browser Action?"](http://antimatter15.com/wp/2009/08/how-i-would-design-the-browser-2-addons/) . But back to the point, this post will detail every little feature that is utterly insignificant in the grand scheme of things that I felt like improving on in the streamie client.

[![](Screenshot-6.png "Screenshot-6")](Screenshot-6.png) Retweeters show a little icon

This is a feature that was in Chromed Bird and Tweetie and was pretty easy so why not implement it.

[![](Screenshot-9.png "Screenshot-9")](Screenshot-9.png) Short links are automatically expanded

This feature is accomplished using Dion Almaer's [endpoint resolver](http://code.google.com/p/endpoint-resolver/).

[![](Screenshot-8.png "Screenshot-8")](Screenshot-8.png) Better link detection

My fork uses John Gruber's [improved liberal, accurate Regex pattern for matching URLs](http://daringfireball.net/2010/07/improved_regex_for_matching_urls). This allows cases like the above to be properly ended at the parenthesis while still allowing wikipedia links that include parentheses.

[![](Screenshot-7.png "Screenshot-7")](Screenshot-7.png) What client was used to post it.

Mine displays what client the poster is using.

You can try it out on [http://antimatter15.streamie.org/](http://antimatter15.streamie.org/) But seriously, all the forking of streamie is probably great for the project, and my role is very insignificant, and it would be great if some of the features got into the master branch :)
