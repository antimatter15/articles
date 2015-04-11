---
title: New Recovery Menu + Reload Animation
author: admin
date: 2008-07-02 6:10:45
categories:
  - Ajax Animator
tags: 

template: article.jade
---

I organized some buttons from the tool menu into a new "Recovery" submenu. It is marked by a shield for it's icon. From it, you can select Reload Canvas, which saves onlypaths, Reload Application, which is what you do when your truly desparate and the app is rendered useless (such as if you type in Ax=null; into the script executor). Now there's a new button, Reload Animation. It tries to save the state of the animation and reloads it, in the process, restarting the timeline and canvas.
