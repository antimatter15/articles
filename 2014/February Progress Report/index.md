---
title: February Progress Report
author: admin
date: 2014-02-28 3:10:20
categories:
  - Meta
tags: 
  - amazon
  - content aware fill
  - context menu
  - flyout
  - image
  - inpaint
  - inpainting
  - navier stokes
  - processing
  - progress
  - projects
  - telea
  - yopnro
template: article.jade
---

> _Work expands so as to fill the time available for its completion._
> 
> — Parkinson's Law
For the past four or so months, I've been working on just one major project. It's rather depressing to think that I built a reasonably impressive initial prototype over the course of about a dozen sleep-deprived hours, and that all I've accomplished since then is minor polish. Technically, there have been at least two rewrites, completely new capabilities and substantially improved technology, but none of that really matters when it comes to describing the project. A project is what it is, at 80% completion, at 95% and 99%.

Second semester at school has started, and that means that Pass/No Record isn't a thing anymore, and everyone else is adjusting their behavior appropriately. Problem is, _I _haven't changed. It turns out that an entire semester of racing toward the bottom is unsustainable when suddenly the floor has been adjusted to above your current position. But the more important point is that it's leaving less time, and in particular, less contiguous time to work on anything.

Last month, I was working on a port of the Telea inpainting algorithm. Inpainting refers to any kind of image processing operation which attempts to intelligently fill in certain regions of an image with other content. Perhaps the most famous implementation of this is Photoshop's Content Aware Fill feature, which uses a texture-synthesis and patch-based system, which enables them to copy over things like patterns, and textures, filling in vast contiguous regions of missing content. The problem is patch-based inpainting is almost always quite slow, in spite of its high quality results. There are simpler algorithms based on the Fast Marching Method like Telea or Navier-Stokes which use diffusion models and the ilk in order to propagate the solid colors of the bordering region of some inpainting mask inwards. I'll write an actual blog post about this once I package it up and build a nifty demo for it.

Last year, Ben Kamens of Khan Academy posted about reverse engineering the flyout menu in Amazon, which suffered from the rather odd behavior of _acting exactly how it should_. You totally should be able to navigate to a submenu without worrying about accidentally mousing over something else. I looked around for a context menu library which could actually do this, but for some reason I couldn't find one, so I decided to make my own.
