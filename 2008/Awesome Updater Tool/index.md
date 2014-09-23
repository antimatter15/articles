---
title: Awesome Updater Tool
author: admin
date: 2008-04-26 7:17:17
tags: 

template: article.jade
---

I've created an awesome little updater tool. Bascially there is a script named "update.php" on the server that is called by a script on my computer which pushes individual compiled files onto the production server (JS/HTML for now, CSS later). Updating is literally 2 clicks. Compile, Auto-Deploy. (or semi-manually, its 3 button clicks)

I even have my own version control system. (simpler than subversion, and more reliable for me- as if you read the svn comments, half of them are me getting angry about svn). It archives all builds. (every time i press the "compile" button) and stores it into a version.js file (which by the way goes into the compile process). Verison.js can have various tags like dev: true, which is detected and gives a small "Testing Release" nag (not really) window.
