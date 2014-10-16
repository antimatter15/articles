---
title: Javascript SHA1 and SHA256 in 
author: admin
date: 2010-01-03 3:38:29
categories:
  - Hash Functions
  - Javascript Distributed Computing
  - Security
tags: 
  - codegolf
  - cryptography
  - penalty
  - sha1
  - sha256
  - slow
  - small
template: article.jade
---

Not sure why I made this, but here's some super tiny implementation of some cryptographic functions. There are some optimizations made for size rather than speed (especially with SHA256), for instance, there are some 71 constants which are used in SHA256 which in most implementations are stored precomputed (they take up around 1KB in hexadecimal), but with mine, they are computed at runtime, which adds a significant runtime penalty, taking twice as long as comparable implementations. It should also be noted that it doesn't do any UTF8 encoding that some other implementations do, but it can be added by UTF8 encoding the text before running it through the functions.

SHA1
<script type="text/javascript" src="http://gist.github.com/267720.js"></script>

SHA256
<script type="text/javascript" src="http://gist.github.com/268113.js"></script>

MIT licensed, but please post a comment if you plan on using it.
