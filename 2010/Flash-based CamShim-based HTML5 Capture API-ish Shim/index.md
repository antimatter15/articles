---
title: Flash-based CamShim-based HTML5 Capture API-ish Shim
author: admin
date: 2010-07-18 8:41:37
tags: 

template: article.jade
---

It doesn't truly cover the entire capture api. In fact, all it covers is the first example they give on using the navigator.device.captureImage function. I can't even figure out if that even complies with the rest of the spec because they seem to be accessing a uri property of MediaFile, which is only defined as an object that extends inherits from File with the extra "format" attribute.

[https://github.com/antimatter15/CaptureShim](https://github.com/antimatter15/CaptureShim)
