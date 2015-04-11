---
title: IE Support
author: admin
date: 2008-06-06 10:09:57
categories:
  - Ajax Animator
tags: 

template: article.jade
---

I've gotten IE to work. Building off what I did to get Opera to work. (BTW. Safari is just like firefox, so no real problems there)

&#160;

It really wasn't as hard as one might imagine. I created a browser sniffing thing to use VMLRenderer for IE and SVGRenderer for everything else. I tested it out. IE worked fine.... except one small thing. The shapes appeared 200px away from where I drew them! Oh Noes! After some experimentation, i discovered that it only works when the canvas is absolutely positioned. But when I do that, my awesome centering doesn't work! So, i made some more browser-sniffing code to detect if it's IE and set positioning to absolute, and make left: 5% so it's not too terribly off-center.

Also, I got rid of some globals, and the canvas size is no longer hard-coded.
