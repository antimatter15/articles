---
title: Wave Gadget API issues (again)
author: admin
date: 2009-09-07 9:40:58
tags: 
  - google
  - google wave
  - wave
template: article.jade
---

So I've been having issues with the Wave Gadget API (again). This one is simple, Wave isn't really real time. So right after doing a submitDelta, you can't get() the data and expect to have the new one instantly.

It's been giving me some problems, but I'm getting around it by using my awesome wave gadget library which will now magically apply the changes immediately so you can access it even before things actually happen.

Also, partially due to this, things would be far more useful if you could get the date of each insertion or deletion.
