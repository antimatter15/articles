---
title: Wikify Format 2.0
author: admin
date: 2008-12-20 5:45:10
tags: 
  - format
  - new
  - wikify
template: article.jade
---

2.0 isn't an actual version number, but i've added the new one.

it's basically

Parent ID (or _body) &gt; Element tag name : Parent Index &gt; format type = patch/innerhtml data

or

_body&gt;div:0&gt;span:1&gt;d=hello!

the formats are p, d, and o, or Patch, HTML, and Legacy, respectively. Patch uses [diff-match-patch](http://code.google.com/p/google-diff-match-patch/), unidiff style data. Patch is the same, and Legacy is an intermediate format of sorts, which is easily converted to from the old formats, but still follows the general pattern of location&gt;type=data. The only difference between Legacy and HTML is that legacy uses a different location scheme.

The pluses of this new system, is that it's more accurate, and your edits are more resistant to page changes. The data is more human readable, the system is more reliable, and stores less data on the server. The cons, are that there is a 20kb overhead in wikify core, and saving may take some more time.
