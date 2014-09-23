---
title: Ajax Animator/OnlyPaths Integration
author: admin
date: 2008-06-06 6:55:15
tags: 

template: article.jade
---

First of all, i don't have a preference, Ajaxanimator, AjaxAnimator, or ajaxanimator or Ajax Animator.

Today marks a milestone release. Where OnlyPaths (the revolutionary new graphical editor for the new Ajax Animator 0.2 releases) is integrated into the product. I don't need to go in depth to explain why the ability to actually draw is important to animation software (hmm...).

But because the overall application is so closely linked to the drawing application, this really enables the rest of the application to be developed.

Currently, it is very limited. Press a small link and draw random rectangles. That's it. The tools have not yet been linked.

OnlyPaths is quite big. It is powerful as well. but it is very big. That's why Prototype had to be eliminated. It was quite big (~120kb), but OnlyPaths is bigger, OnlyPaths itself is 36+90+66=192kb. Richdraw was 10+9+7+120=146kb, without prototype, RichDraw would be a mere 26kb. Not to mention, that Ext 2.1 is bigger that Ext 1.1 (meanwhile bringing more features, etc.).

josep_ssv's mondrian style color picker will be integrated (in a later version). I think it would fit nicely into the accordian right-panel as a sort of advanced color picker tool.

Meanwhile, I sort of copied the flash UI with the addition to the "hide timeline" button. BTW. a shortcut for that button (which doesn't yet work) is to doubleclick the fine outline between the canvas and the outline.
