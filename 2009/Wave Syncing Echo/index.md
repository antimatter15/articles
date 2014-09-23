---
title: Wave Syncing "Echo"
author: admin
date: 2009-09-15 4:39:17
tags: 
  - api
  - gadget
  - wave
template: article.jade
---

The problem with the implementation of lots of things like VectorEditor, SVG-edit and the Ajax Animator is that something i'm going to randomly call "echo".

Basically, you might delete something on your client, and right after that, since the result isn't real time, the app adds the shape back, and it gets deleted again. With multiple users, it gets more confusing, and there's a random chance that it might not even delete.

In wave2 which is now a really complicated and massively slow library filled with tons of inelegant crap spanning almost 600 lines, the way it's resolved (somewhat) is by not truly deleting things, but rather replacing it with DELETED/TIMESTAMP.
