---
title: jailbreakme.com
author: admin
date: 2010-08-01 8:27:24
categories:
  - Blog
tags:
  - apple
  - iphone
  - jailbreak
template: article.jade
---

I couldn't resist looking into the source of it. It is obfuscated a bit, but there are some interesting parts. Example: How it detects device models.

For iPad, well there's just one iPad so they just search the UA string for iPad and it's totally iPad1,1\. iPhone 4 is detected by the global devicePixelRatio property, because[ the pixel is dying](http://aralbalkan.com/3331). Differentiating between iPhone models (not just firmware versions) is pretty awesome. They do a speed test. Specifically, [SunSpider](http://www2.webkit.org/perf/sunspider-0.9/sunspider.html). It's pretty much the de-facto standard web benchmark nowadays, and it was also started by Apple for the Webkit project.

Apart from that, the exploit itself is PDF based. Which is interesting as Adobe Reader [accounted for 80% of exploits](http://www.computerworld.com/s/article/9157438/Rogue_PDFs_account_for_80_of_all_exploits_says_researcher) in 2009\. However, iOS's implementation is probably totally independent, but it's neat seeing this happen. The exploit is located at http://jailbreakme.com/_/device_model/device_firmware.pdf. For example, the iPhone 4's URL would be http://jailbreakme.com/_/iPhone3,1/4.0.pdf. The resulting file is 12.9KB. I assume it's some pretty standard attack code because I'm not a hacker and I know absolutely nothing about that.
