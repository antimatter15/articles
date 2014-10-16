---
title: Updates Today
author: admin
date: 2008-05-06 7:20:26
categories:
  - Ajax Animator
  - OnlyPaths
tags: 
  - browser
  - button
  - cellactions
  - daily updates
  - drawings
  - editor grid
  - features
  - icons
  - layers
  - onlypaths
  - properties
  - prototype
  - z-index
  - zoom
template: article.jade
---

http://antimatter15.110mb.com/animator/Animator2/build/ajaxanimator.htm

Now, its at Ajax Animator Build 48\. It has an improved "Properties" menu. The Drawing icons have been updated (to give you a taste of features of OnlyPaths that will be added). Notice that there are some features left out. Zoom will be done via the zoom button on the canvas toolbar, and panning won't be necessary. I'm curious of whether I should or should not include the z-index ordering. Simply, the whole purpose of layers is that. and Layers seem much more managable, visible, and such.

Speaking of layers, the Layer browser part of the timeline has been added. It is currently just a simple Editor Grid (so you can inline edit the label!).  I'm going to add http://cellactions.extjs.eu/ for the ability to remove/edit layers via a nice icon.

I have also almost sucessfully ported OnlyPaths to ExtJS. it turns out, that all prototype code is in richdraw.js, and it is as simple as replacing prototype code with Extjs counterparts.

such as
this.blahlistener = this.blah.bindAsListener(this)
Event.observe(this.explosion, "mouseexplode", this.blahlistener)

becomes
Ext.get(this.explosion).on("mouseexplode",this.blah,this);

Often, Ext code is simpler, and more consise, but other times it is not so.
