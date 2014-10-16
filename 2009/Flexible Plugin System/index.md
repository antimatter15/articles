---
title: Flexible Plugin System
author: admin
date: 2009-01-15 11:28:18
categories:
  - Uncategorized
tags: 
  - CMS
  - mod
  - plugin
template: article.jade
---

Basically, in modern CMS development, there are 2 types of plugin systems.  (that i care to talk about)
A) creating a comprehensive API and isolating plugins into a plugin directory (wordpress does this, AFIK)
B) creating patches to the source code through complex patching instructions (usually combined with an API too, and SMF sorta does this-ish)

The problem, is that neither is really developer-friendly (or at least me-friendly). Learning an API is boring, and I see recognize code better than man-pages. Documentation also is normally pretty crappy anyway (except for big projects like WP/SMF). Patching source code makes you manually define the context, line number, etc. It's usually using a non-standardized system (XML files) and has many merge conflicts.

So how can it be improved? Well, the API part can't really be improved on, but the latter one can. I think just hacking away directly at the source code is pretty decent. Because many times the changes are minor, and it doesn't make sense to make huge new plugin files for it (though it would still work).

Instead, imagine something similar to a SCM like CVS or Subversion. Use patches in standardized formats (GNU Diff Unified format), so people can resolve conflicts with familiar tools, and reduce the chance of it happening. Have the CMS include a "developer mode" which enables the system to intelligently find the edits and build patches for.

What that becomes, is a simple, flexible pluggable, portable plugin system. (yay! a plugin subsystem as a plugin!).

It's really just to streamline the (B) type of plugin system.
