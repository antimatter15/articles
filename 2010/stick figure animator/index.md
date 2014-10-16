---
title: stick figure animator
author: admin
date: 2010-06-22 9:29:03
categories:
  - Ajax Animator
  - Stick Figures
tags: 
  - ajax animator
  - animations
  - blue
  - buttons
  - edit
  - experiment
  - frames
  - ipad
  - microsoft
  - original
  - pivot
  - raphael
  - shiny
  - stick figures
  - stop motion
  - upload
template: article.jade
---

[![](http://antimatter15.com/wp/wp-content/uploads/2010/06/Stick2-αq-Chromium_063.png "codenamed stick2")](http://antimatter15.com/wp/wp-content/uploads/2010/06/Stick2-αq-Chromium_063.png)

One thing the ajax animator's pretty bad at is stick figures. Sure it's not impossible, but it can't really compare with the ol-fashioned frame-by-frame joint-manipulation likeness of [Pivot](http://www.google.com/images?client=ubuntu&amp;channel=cs&amp;q=pivot&amp;qscrl=1&amp;um=1&amp;ie=UTF-8&amp;source=univ&amp;ei=GF0hTJejE4H98AaJ0qxg&amp;sa=X&amp;oi=image_result_group&amp;ct=title&amp;resnum=4&amp;ved=0CDQQsAQwAw). It's called stick2 because the [original experiment ](2010/02/stick-figures/)with stickfigures was named stick.html, and when I went to extend it and didn't feel like setting up a git/svn repo, I copied the file and named it stick2.html, and with no good project-naming skills, it stayed that way.

Anyway, this was a project that got pretty close to completion in early march, but I never bothered to blog about it until now. It should work pretty not-bad on an iPad J(except the color picker), though honestly, I've never tried it.

The interface is pure jQuery/html/css. The graphics are done with Raphael, but the player actually uses &lt;canvas&gt; for no particular reason.

Basically, it's organized into two panels, the left-side figures-box and the bottom timeline. The figures-box contains figures (amazing!) and clicking on them adds them to your canvas. The two defaults are the pivot-style stickman, and something called "blank" which is a root node with no additional nodes. Though it shows up as a orange dot, unless you add something to it, it doesn't have any actual look when viewed in the player.

On top is the context-sensitive buttons. Well the buttons in my screenshot aren't context sensitive, they're permanent. But when you click on a node, a new set of buttons (and words too!) appears. One is a line and the other is a circle. Click them to add a new segment or circle to the currently selected node. Then are various settings for the current segment (each node other than the root one is associated with a segment). Clicking those allows you to modify them. Also, a red X appears on the right, and that basically means remove the node and the child nodes.

So, now you have some extra nodes, how do you change them? Simply hold it down and drag, and the the segments move as well. But note that the length of the segment doesn't change as you move it. That's because by default, it locks the length of the segments. There are two ways to get around it. The first is to hold shift while dragging. The second is to tap the little lock icon on the top left.

On the bottom, is the timeline with live-previews of your frames with a semitransparent gray backdrop of numbers. Switch between each one by clicking on them and add one at the end by hitting the green "Add new frame" button.

On the canvas, there are two yellow squares, those allow you to resize the canvas.

On the very left of the top toolbar, is the play button. Hit it and the figures toolbox minimizes and it plays out your animation. Click it again to get back. Then is a little upload button. Hit it and then a little box pops up with a link to where you can find your animation in a way that you can share and to edit (not actually edit, but more like fork, as each save is given a unique id). Next is the download button which you hit, and get prompted by a big prompt-box which you use to paste in the ID of the animation you (or someone else) has saved, so you can edit it. Most of the time that's useless as when you send a link with the player, it has a button which says "Edit".

Sample animation: [http://antimatter15.com/ajaxanimator/stick2/player.html?rlsm4lx14c](http://antimatter15.com/ajaxanimator/stick2/player.html?rlsm4lx14c)

Try the application out: [http://antimatter15.com/ajaxanimator/stick2/stick2.html](http://antimatter15.com/ajaxanimator/stick2/stick2.html)

Code: [http://github.com/antimatter15/stick2](http://github.com/antimatter15/stick2)
