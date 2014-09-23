---
title: Slower Development
author: admin
date: 2008-01-17 6:05:12
tags: 

template: article.jade
---

Development has been slowed, because of the huge task i'm doing (upgrading to ext 2.0), and i've been interested in different projects. I have started development on a desktop flash IDE (much more drawing functionality-faster etc.) coded in C# (which i suck at). i also am working on a stop-motion animation studio (nothing much, just to test my skills, in VB.NET), and a filesystem mounting stystem (also VB.NET)

The desktop flash ide is somthing i'm hoping can be done in less than a day. Which for proprietary applications is impossible, but i'm demonstrating the micacle of open source, i'm building off of a built SVG engine (SVGPaint). So all i have to do, is to hack into it's saving mechanism and save automatically to an automatically generated filename, and build an application that creates an xml file that links to all the SVGs (swfmill parses XML, and it supports importing SVG!) Making the XML should be as easy as appending a string from a for loop. and hacking the saving engine should be easy if i can pinpoint the code. After that is done, i'll leave it to the community.
