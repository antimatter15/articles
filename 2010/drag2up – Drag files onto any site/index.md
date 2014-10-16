---
title: drag2up – Drag files onto any site
author: admin
date: 2010-10-01 5:44:19
categories:
  - Chrome Extensions
  - drag2up
tags: 
  - chrome
  - drag
  - drop
  - extension
  - files
  - google chrome
  - html5
  - images
  - upload
template: article.jade
---

<object classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" width="640" height="505" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,40,0"><param name="allowFullScreen" value="true" /><param name="allowscriptaccess" value="always" /><param name="src" value="http://www.youtube.com/v/TQJppLl_r8w?fs=1&amp;hl=en_US&amp;hd=1" /><param name="allowfullscreen" value="true" /><embed type="application/x-shockwave-flash" width="640" height="505" src="http://www.youtube.com/v/TQJppLl_r8w?fs=1&amp;hl=en_US&amp;hd=1" allowscriptaccess="always" allowfullscreen="true"></embed></object>

Drag2Up, is an app named horribly, as I suck at naming things. It's very simple in terms of capabilities - no buttons, no interface, which is pretty much the ideal type of user experience, something that's intuitive and lends focus to content, not chrome. Really, this post isn't useful in any way. What you should do, is [install it](https://chrome.google.com/extensions/detail/bjgjolhpdlgebodaapdafhdnikagbfll) and try it out for yourself (Chrome only, It would be possible to make a firefox version, but I have no experience with Firefox extensions, and the new Jetpack isn't quite out yet, though you can probably adapt the code relatively easily. Maybe a greasemonkey script by using GM_XHR). [https://chrome.google.com/extensions/detail/bjgjolhpdlgebodaapdafhdnikagbfll](https://chrome.google.com/extensions/detail/bjgjolhpdlgebodaapdafhdnikagbfll)

Drag and drop is probably one of the greatest forms of interaction ever, it's intuitive and exemplifies the usefulness of a GUI. Recently, browsers have implemented drag and drop APIs (actually a [feature of IE5.5+ ](http://www.quirksmode.org/blog/archives/2009/09/the_html5_drag.html)but then codified into part of HTML5). Some browsers, namely Chrome and Firefox implement a dataTransfer property of the drop events that allow one to access files dragged from the user's desktop (or file browser) onto a web application. The application can read the file through the File API, and do whatever it chooses. Probably most notably is Gmail's utilization of the feature that allows dragging and dropping files from the desktop onto a message to upload it as an attachment. When it was announced, some people remarked how excited everyone was of a feature that was present in desktop clients for several decades already.

[![](128.png "128")](128.png)

Browser vendors have the role of enabling developers to do cool stuff. It's up to a web developer or service to maintain an application, to update it and add new features. Undoubtedly, many do, living on the bleeding edge of innovation, but most don't, and stay locked in a certain state for years if not longer. Extension developers have no obligation to be entirely objective in terms of how it deals with websites, and many are site-specific, adding features to sites that lack them, integrated into the interface, utilizing product-specific APIs, or document structure. Browser vendors enable innovation, site developers integrate standards and browser extensions add features to sites, because the developer is unwilling or because of restrictions on the functionality of web apps (x-domain, persistence, etc).

Uploading images is a fairly common task, and the standard go-to-file-host-site, click-the-attach-button, browse-button-hitting, navigation-through-folders and waiting-for-page-to-reload-after-uploading, link-copying, tab-switching and pasting. Some applications like [CloudApp](http://www.getcloudapp.com/) look promising in alleviating this needlessly tedious process, but only reduce the interaction steps a little. The ideal would be making that third-party file upload service integrate seamlessly into all web applications, with a level of integration akin to Gmail, drag and drop.

As awesome as it sounds, it's not as easy to implement as one might like. The basic idea was to detect when a drag event started, and to iterate all the elements, adding an absolutely positioned, semitransparent mask to indicate that it's a drop target. A few issues occur with that, I have [a little writeup on those issues](2010/10/gmail-style-html5-dragdrop/).

A lot of WYSIWYG editors use iframes, and creating content scripts with all_frames: true doesn't necessarily mean it runs on all frames (for some very odd reason). And also for some reason, there's no way to access frames from window.frames in content scripts. So I have this hack where if there are frames, it injects some javascript into the real page executed in the page's context to run it within the iframe (if it's the same domain, as it always is in wysiwyg editors). Then events get propagated from the sub-frame into the parent window, through postMessage that is subsequently handled by the content script, forwarded to a background page using chrome.extensions.sendRequest, and it all happens in reverse once the server gives a response. As such, it's a really bad idea to use this for large files since it needs to be passed around several times over several pages, and apparently [V8 isn't the best with big strings](http://blog.andrewvc.com/node-js-and-binary-data).

Aside from that, uploading to imgur for some odd reason takes a long time. I don't like sites that don't have simple JSON POST APIs, and there really aren't many that fit that criterion. So with the initial release, images are uploaded with imgur and text files are all uploaded to a github gist.
