---
title: Animation Playback/Pause Bookmarklet
author: admin
date: 2008-06-17 8:14:38
tags: 

template: article.jade
---

in the new "beta" system, you can't play animations you've created. Its supposed to be that when you press the Play button from the animation menu, you get flipepd over to the preview tab where yoru animation starts off. The player tab isn't done yet, so there's no way. Here is a bookmarklet hack that will let you automatically flip through the the first 10 frames at 10fps.

javascript:<span class="objectBox objectBox-string">%28function%28%29%7BAx.controls.play%3Dfunction%28%29%7BAx.player%3DsetInterval%28function%28%29%7Bif%28Ax.tcurrent.frame%3C10%29%7BAx.controls.next%28%29%7Delse%7BAx.selectFrame%281%2CAx.tcurrent.layer%29%7D%7D%2C100%29%7D%3BAx.controls.stop%3Dfunction%28%29%7BclearInterval%28Ax.player%29%7D%7D%29%28%29</span>

Just run the bookmarklet, and the Animation-&gt;Play/Pause buttons will magically start working.

In actual link form: [Ax2 Enable Play/Pause]( javascript:%28function%28%29%7BAx.controls.play%3Dfunction%28%29%7BAx.player%3DsetInterval%28function%28%29%7Bif%28Ax.tcurrent.frame%3C10%29%7BAx.controls.next%28%29%7Delse%7BAx.selectFrame%281%2CAx.tcurrent.layer%29%7D%7D%2C100%29%7D%3BAx.controls.stop%3Dfunction%28%29%7BclearInterval%28Ax.player%29%7D%7D%29%28%29 )
