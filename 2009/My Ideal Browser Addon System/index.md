---
title: My Ideal Browser Addon System
author: admin
date: 2009-08-22 7:28:53
tags: 

template: article.jade
---

A rephrased version of my previous post, but this one is slightly more specific and some more stuff.

I was thinking that since lots of people/companies are trying to make the browser a lot more OS-like, or at least trying to stop you from using anything outside a browser. What does the browser really need to improve?

My idea is that projects like Jetpack, Greasemonkey (to a lesser degree), the Chrome extensions system (havent even looked at it tough, I'm just judging based on lack of media attention), and everything that Microsoft does (things they do are _inherently_ <span style="text-decoration: underline;">wrong</span>) are not going the right path. Jetpack is closer to right (duh, it inspired this post), and Greasemonkey is the closest to right (Jetpack took off the Greasemonkey idea, but took the wrong turn, IMO).

What they're focusing on, is not to overlap with what the W3C and WHATWG does by semi proprietarily developing product-specific innovations. What I think is that Web Pages should be the same thing as extensions. The HTML standard needs a notifications API, because we already have alert() and something less annoying is not at all a security issue. With that, half of the jetpack apps, which are notifiers can be implemented totally as a web page. No different APIs, no special install things, and for the heck of it, no installing! It's the whole Web philosophy that made the Web work, attached to what adds to the web.

What I think is great about my idea (other than being my idea), is that your Application can now be the same page as your Information and Install page. While Jetpack could integrate Information and Install, and Firefox's XUL/XPI system before it needed a page for info, a install window, and an application interface. With this consistent system, ultimately, things are harder to confuse and you can get to what you're trying to do more intuitively and consistently.
After that, they need a way of making tabs persist and become "background" (which would be a tab but with only an icon, so it's unobtrusive). Then you can replace the functionality of most addons. Browsers that do not support persisting and background tabs gracefully degrade and allow for slow and smooth adoption.

The biggest part is a browser web page permissions system, which the web desperately needs, and the Web browser vendors and plugin makers are attacking in the totally wrong way. Not totally wrong, but totally inconsistent. Think about it, Flash has a sub-window in a flash animation to enable access to webcam/audio, Gears makes a distracting box pop up, and Firefox's geolocation system makes a bar appear on the top. Imagine when they try to add more (HDD storage, Webcam, Sockets, Audio, Microphone, Fullscreen, Printer, loading files, etc), you have 6 bars stacked on top of each other and a infinite loop of modal windows that pop up to ask you for where you live.  Whatever each vendor cares to do, I don't care, but I want that all to be consistent. So why not some HTML tag (maybe a meta rel=feature) and a JS queryFeature (or whatever they wanna call it), and it makes a semitransparent pretty drop down menu on the top right of the page which shows checkboxes for the page to enable (and it would only have the 1-2 features the page is asking for, so it's not hard at all). Anything the browser doesn't yet implement can be disabled with a little tooltip saying "Feature not available" for more graceful degrading.

The permissions system could fix tons of things intentionaly removed from the HTML5 standard for security. The fear for providing an API for Fullscreen &lt;video&gt; was that someone could have a fullscreen video that resembles someone's computer and does super evil spyware or something. Having a permissions system like the one above totally removes that issue.

The permissions could be anything, access to subframes, controlling other tabs, etc. Anything that is a security issue that could still be useful can be put into the permissions system. The things could be color-coded based on dangerous-ness, etc. Anything could be implemented as a web page.
