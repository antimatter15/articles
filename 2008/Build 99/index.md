---
title: Build 99
author: admin
date: 2008-05-27 5:45:17
categories:
  - Ajax Animator
  - OnlyPaths
tags: 
  - browser
  - build
  - color picker
  - commas
  - json
  - later
  - onlypaths
  - stable
  - unstable
template: article.jade
---

Its now at Build 99\. I feel that not much more can be done without the critical OnlyPaths component. I don't have anything ready yet. An Ext port of OnlyPaths is underway, but it is not necessarily very stable, and some critical features (cross-platform drawing API) is not completed yet.

I rolled back one thing yesterday: the Advanced Color-Picker tool. They _will_ be added again later, but I don't want to aim _too_ high for the initial 0.20 release, or else it may never get released. The standard (albeit small) color picking system is fine for now. It also is quite big, so not yet.

IE and Opera should work flawlessly now (Aside from browser-limitations). Most problems in the app are caused by those annoying commas in JSON errors (IE/Opera don't like it when its {blah:stuff,super:happy**<span style="text-decoration: underline;">,</span>**})
