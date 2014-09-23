---
title: Wikify Diff Engine
author: admin
date: 2008-12-18 10:40:31
tags: 
  - diff
  - jQuery
  - tree
  - wikify
template: article.jade
---

So i built a pretty crappy tree-diff system for Wikify. It completely ignores the creation of new nodes, or the deletion of the nodes, but it works most of the time. It's tree based, so the data is fine-grained to the level of however small the nodes are made to be. But many pages with huge paragraphs or such, have huge nodes, and editing a single word would mean saving a huge amount of data.

So Wikify will now use both the tree-based diff (which is great for HTML/XML docs, as they are trees) and divide the changes into text and do text diff for that. Right now, the only thing sutable is the google-diff-match-patch project, which is absolutely amazing, except for how huge it is. But I figure its okay, because I'm already including the (relative) bloatness of jQuery... (especially compared to vX)
