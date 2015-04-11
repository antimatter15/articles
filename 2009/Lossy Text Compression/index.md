---
title: Lossy Text Compression
author: admin
date: 2009-07-26 2:00:09
categories:
  - Data Compression
tags:

template: article.jade
---

So i had this idea to make a lossy text compression system. For those who don't know the difference between [lossy](http://en.wikipedia.org/wiki/Lossy_compression) and [lossless](http://en.wikipedia.org/wiki/Lossless). Well, the main rationale is Wikipedia, I have a jailbroken iPhone and one of my favorite uses of it is the Wiki2Touch (which is now defunct, with the development blog gone and the google code project deleted). The rate of Wikipedia's growth is close to a gigabyte a year. Extrapolating that growth, it will be soon that my iPhone 2G with 8GB of space will run out of room for Wikipedia. Now, the size is almost 6GB (bzip2 compression). Soon, it will approach 8gb - (200mb (root partition size) + 100mb (music) + 0mb (video) + 1gb (apps).

After [googling](http://www.google.com/search?q=lossy+text+compression&amp;ie=utf-8&amp;oe=utf-8&amp;aq=t&amp;rls=com.ubuntu:en-US:unofficial&amp;client=firefox-a) the concept, [it](http://www.halfbakery.com/idea/Lossy_20Text_20Compression) [doesn't](http://cs.fit.edu/~mmahoney/dissertation/entropy1.html) [seem](http://it.slashdot.org/article.pl?sid=06/08/13/200254&amp;tid=98) [very](http://science.slashdot.org/article.pl?sid=07/07/10/0055257) [original](http://cs.fit.edu/~mmahoney/compression/text.html#1330). Even the compressing wikipedia idea doesn't seem original! But there are some limitations to the current world-record breaking systems, they are very memory-intensive (won't work on an iPhone!) and are also very slow (hitchiker's guide isn't/shouldn't be slow!).

So here are some, somewhat inspired ideas for this lossy wikipedia encoding. Since the Wikipedia text is quite normal, capitalization is quite unnecessary and can be added automatically later on. It can search for words in a dictionary and use their indexes for the words (or even short phrases). Words that are not in the dictinonary can be searched in a large dictionary/thesarus and replaced with an appropriate synonym. After that, the data could be compressed with some bz2 or 7zip encoding.

It's quite fast to decode each section with bzip or something, and just looking up the words in the dictionary index (which can be made to use little memory, because I've done so in a spell checker a few days ago).
