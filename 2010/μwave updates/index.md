---
title: μwave updates
author: admin
date: 2010-06-03 2:34:26
categories:
  - Google Wave
  - Microwave
tags: 
  - ajax
  - google
  - google wave
  - javascript
  - microwave
  - tasty food
  - update
  - wave
template: article.jade
---

[![](microwave62.png "μwave June 2 Wave View")](microwave62.png)[![](microwave62s.png "Microwave June 2 Search")](microwave62s.png)

[Over a few days,](2010/05/%CE%BCwave-lightweight-mobile-wave-client/) things can change fairly quickly. There have been several **speed improvements**, a new **Forum-Style blip rendering** option which arranges blip linearly by the time edited with each containing a formatted quote of the parent to establish context. **Attachments** are now fully supported, including thumbnails and download links. The operations engine was totally rewritten which uses asynchronous XMLHttpRequest, a new callback based system and support for a batch operations (which means fewer requests and faster responses). A wavelet header containing a list of all participants in the entire wave has been added, as well as an **Add Participant **button. A **specialized, extremely fast gadget viewer **was added, which allows for blazingly fast rendering of two popular gadgets (and more will come), it works by bypassing the entire gadget infrastructure and loading trusted code directly inline with the DOM. There is a "New Wave" button which allows people to **create new waves directly from the client**. The OAuth backend was authenticated with google, for more secure login transactions. Blips have a **new context menu** which allows for features such as **Delete Blip, Edit Blip and Change Title**. A [full changelog can be found here](http://antimatter15.com/misc/read/?googlewave.com!w+mrqWFs0vA).

[Try it out.](http://micro-wave.appspot.com)
