---
title: Google Wave Gadget API "Flaws"
author: admin
date: 2009-08-12 6:38:36
tags: 
  - flaws
  - google
  - realtime
  - vector
  - vectoreditor
  - wave
template: article.jade
---

Edit: This post is mostly crap. I figured out how to solve my problems while writing this. But I'm posting it anyway because I feel obligated to spam the internet with my outdated thoughts

One of the main features of Google Wave is the ability to do live concurrent realtime editing. Sadly, this functionality isn't easy or as far as I know even possible on Google Wave.
Most of the time it doesn't matter. The only time it would matter is if you are using live concurrent text editing within the gadget. Of course, that's what I tried doing and that's why i'm writing this blog post.
So I still haven't gotten my Google Wave Invite yet (hope soon!) so I'm experimenting with the pygowave project, which is a third party open source implementation of the Wave Protocol. The interface is missing something that is quite important to wave: multi-user text editing. So I decided to try implementing it as a Wave Gadget.

I really did understimate it's complexity. While implementing isn't usually too hard, the structure of the Wave Gadget API makes it more difficult than it could/should be. What the wave gadget API does is it has a real time updating key-value table. It's quite flexible and useable most of the time, but for real time editing, not quite as useful as when something is changed.

For instance, if 2 people are editing the same thing, then whoever submits the data last is the one which wrote the data and the first person's edits are ignored. Very rarely do 2 people *need* to edit the exact same thing. But when they do, it's not easy to merge the things. A more chat-like system could work.

But while implementing that chat-type system on top of Wave is possible, it feels very inefficent, partly due to everything being cached at all states (to support Playback) and worry about something akin to garbage collection to delete things after everyone has patched their running copy.
