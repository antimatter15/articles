---
title: Opera 9.25 Support
author: admin
date: 2008-06-06 9:38:28
categories:
  - Ajax Animator
tags: 

template: article.jade
---

If you have Opera 9.5 it already should work. But Opera 2.5 (the current stable version) had issues. The createUUID function uses the Array.map() function. This comes native in Opera 9.5 and Firefox, but not in Opera 9.25\. After figuring that out, I made a version of the function that didn't use Array.map. Now it's fine. 

It still renders the shapes a bit awkward (again, 9.5 is fine).

&#160;

...Now to get killed by IE :)
