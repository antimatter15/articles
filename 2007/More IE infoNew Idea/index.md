---
title: More IE info/New Idea
author: admin
date: 2007-12-22 6:02:02
categories:
  - Ajax Animator
tags: 

template: article.jade
---

Okay, so before I thought it was purely impossible due to the inability for javascript to prototype the HTMLElement object. I just discovered, i could just replace all refrences to setAttributeNS(null,blah,stuffy) with the normal setAttribute(blah,stuffy) and it will still work under all browsers. This means i don't have to modify the HTMLElement prototype, and all i have to do is to create a document.createElementNS function.

Then IE would be leveled with all the other non-svg yet-fully-standards-compliant browsers.

The non-svg browsers all have the ability to do everything that a normal svg supported browser can do, but you just can't see the stuff - until you preview the flash animation. I guess it's not as bad as a huge semi-biased error message.
