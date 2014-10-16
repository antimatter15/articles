---
title: Why the Chrome Web Store is Bad for the Web.
author: admin
date: 2011-06-02 9:22:45
categories:
  - Chrome Extensions
tags: 
  - apple
  - applications
  - awesome
  - bad
  - chrome
  - church of google
  - crx
  - evil
  - firefox
  - install
  - iphone
  - longpost
  - mozilla
  - open
  - rant
  - web
template: article.jade
---

_Note: I've changed a few things that will hopefully make my point a bit more clear_

Apple got it right in 2007.

If you've read any of the other posts in this blog, you will probably come under the assumption that I'm a devout follower of the Church of Google. Thus it will probably be quite a surprise to read the headline, something which appears downright sacrilegious: it questions the infallibility of the great Google. But I try very hard to maintain some semblance of objectivity and rationality, and this post will be about why I think the Chrome Web Store is bad for the web.

The Chrome Web Store is the applications and extensions gallery for Chrome. It's Google's centralized repository and directory for discovering Chrome-related things. Just hearing the name of it, you can probably tell, it's likely quite inspired by the iOS/iTunes/Mac App Store. It's not because they aren't able to innovate (or it might, but I won't take that view), but it's probably the result of the huge App Store boom. It's not that even what Apple did was particularly innovative, but somehow it managed to secure billions of dollars for the company, and all it's competitors quite rationally want a chunk of it. This however, isn't about improving the state and future of the web, but rather the indulgence of buzzwords.  This post isn't only about the Web Store, but rather the entire Chrome Applications and Extensions systems. From distribution to installation and the user experience afterwards.

## Introduction.

There are two types of installable web applications that exist in the Chrome Web Store: hosted apps, in other words "glorified bookmarks", and packaged apps. Glorified bookmarks are relatively hard to create, expensive and have no real additional functionality. Packaged applications evade the standardized mechanisms for offline web properties and eliminates many of the advantages of web apps in the first place.

Chrome's developer overview for creating installable web apps describes the system as a solution to one, rather insignificant, problem. It's the problem of permissions escalation: some technical detail that hardly seems important. Put simply, it's that users get annoyed when they're asked to hit "Okay" to annoying permissions prompts. And so Google's solution is to invent a certain class of web site which has different security properties, where all the permissions are put into a single prompt.

To users, however, the existence of a web app is a solution to a much different user experience problem: they want to hit nice large pretty icons to go to sites which they frequently visit. But somehow, the solution they opted for creating these large clickable bookmarks is quite terrible. The only user-facing purpose of installable applications is the ability to bookmark with a large icon, something that Apple got right with iPhone OS in 2007.

## Apple got it right.

I love those four words in that order, it feels so sensationalist and rebellious. But before the Cult of Apple leaps on that statement, notice the wording "Apple _got_ it right". It doesn't strictly mean that whatever Apple's doing _now_ is right, just that what it _did_ is right. In fact, that's exactly what happened. Apple got it right, then made it different, and Google made it wrong.

First, we need to recall the distant year of 2007\. It was quite a while ago, and I won't pretend that my memory is that great. But it was a long time ago, a full year before the first beta release of Google Chrome. The iPhone was released with it's plethora of eight apps and no ability to install more. The App Store didn't exist, and the closest semblance was the Installer.app for jailbroken devices (Cydia came later).  A few months later, Apple released a series of updates, and Steve Jobs signaled what he believed to be the future of iPhone applications: The Web. It doesn't come surprising that Apple's Mobile Safari was and likely still is (more or less) the best browser for any mobile device.

The important aspect is the _way_ these web applications were installed. You went to Mobile Safari, and browsed around. You found a web app, and you used the web app the _way the web was intended_. No installations, you just navigate to a URL and start using it. You find the app useful and/or awesome, and you "bookmark" it.  But, instead of actually doing the browser "bookmark", you hit the button right below: "Add to Home Screen". It asks you for a name for that application, automatically prepopulated with the document page title. You hit "Add", and you now have a nice, shiny icon on your home screen. You can hide the browser chrome and it becomes indistinguishable from the normal native application experience.

That app icon is just an image URL specified with a single meta tag. It's totally decentralized in every way, and represents the openness and simplicity that simply _makes sense_ for this platform. All a developer needs to do to enable their web site to turn into a fully fledged web application is to add a `&lt;link rel="apple-touch-icon" href="/customIcon.png"/&gt;` in the head section of the page.

Contrast that with what Google requires: creating a Google checkout account, entering credit card information, navigating to the Chrome Web Store page and clicking several links in the footer in order to navigate to the page where you have to pay $5 for creating an app, create several icons, copy the manifest.json template and editing some values pointing to the icon locations, going to chrome://extensions, enabling developer mode, adding the unpacked app to make sure that it works, then going back to the original directory, zipping it up, and uploading it to the Chrome Web store, where you have to write a description, add screenshots, reupload an icon, publish, wait ten minutes, and then spam the internet with that link and edit your site's code to point to that page. It's an awful much to go through in order to _just create a bookmark_.

## Apple turns evil.

This subtitle is intentionally misleading. I don't really think Apple's evil, but that loaded four letter word is much more concise than the more appropriate phrase "Apple adopts a new platform and shifts ideologically to favor a system which is ultimately in conflict with and entirely inapplicable to the web in its current state or in the foreseeable future".

Apple's prescience of the power of the web was sadly a bit anachronistic. The web technologies that would enable their vision _were not yet ready_. The second browser wars haven't really even begun, and the jailbreakers, despite handicaps, still managed to develop that platform more than the officially sanctioned web developers could. Browsers were too slow, hardware was to slow, there weren't enough features, not enough could be done, and the paradigm was not well understood.

Apple followed the lead set by the jailbreak community and launched their own native application development and distribution system: The App Store. It was a hit, and soon became a super huge buzzword. It an all that it represented: centralized one click micropayment driven mobile advertising funded indie developer weekend novelty apps.

<span style="font-size: 20px; font-weight: bold;">Google gets it wrong.</span>

So there was an App Store craze, and everyone wanted one. So it logically follows that Google built an App Store. But the web had no notion of _apps_. There were web applications, but they weren't rigidly defined as apps.  This is where Google got it wrong. The Chrome Web Store needed to sell apps, and had to create a dichotomy out of the web in order to do so. It created a distinction between web apps and websites where none had existed and shouldn't have ever existed.

<span style="font-size: 20px; font-weight: bold;">The false dichotomy.</span>

Steve Jobs said that on Mobile, people want Apps, not websites. Before blindly mimicking the concept of apps on another platform, one should probably explore _why_ users like apps over websites. It's because the mobile app offers a _better mobile-optimized _interface to whatever they're doing.

Websites aren't generally designed for mobile, they are often slower, and can't make use of persistent user interface elements like a tab bar. Apps aren't popular because of the existence of the App Store. It's because there's additional value provided in having those apps, that users use the App Store to get them.

However, web apps, just like websites are optimized for normal computers. Web apps are no better than web sites, and when web apps really have nothing to provide, their respective web stores are useless.

One purported reason for creating the distinction between apps and websites is to give developers the opportunity to charge for the application in the web store. But why should the ability for an author to receive money for his or her respective works be exclusive to web apps? Why not all web sites?

While it's quite clear that if anything meant to supplant a desktop application and is built for the web can be considered a "web app", nearly everything else exists in a sort of gray area. Facebook, Twitter and the other social networking are predominately content focused, but have some app-like characteristics, and so they could be considered "web apps" too, despite how there aren't really desktop equivalents. But what about sites like the New York Times? Pure content sites would logically seem to be the farthest one can go from the concept of an "application". It's clear that _any_ web site can be considered a web app.

Since anything can be considered a web app, the Web Store is a mere directory of a certain number of websites. It's a limited subset of the internet with terrible discoverability properties restricted only to sites where the owner (or a particularly devout fan) is willing to pay $5 in order to allow a subset of users to _bookmark the site_. It's proprietary, no other site can have quite the same properties as _the_ web store because Google has the Web Store URLs hard coded into chrome somewhere. Searching in the web store really isn't that great either, with no ability to search reviews, no pagerank, no search operators, no ability to search within the content of apps. You would figure that if Google were to clone a subset of the internet, at least they would get search right.

This closed, exclusive and excessively tedious process for creating mere bookmarks attacks some of the web's traditional benefits and ideals.

## Packaged applications.

The above sections dealt with how the "glorified bookmarks" are useless and downright harmful. There is a second class of applications which are similar to the former in that they also get a pretty large prominent and clickable icon, but different in that they actually provide functionality that is different from mere ordinary websites. Its virtues include that they tend to work offline and have the ability to do certain things that normal web apps can not do. However, it pretty much stops there.

Packaged apps work offline, but their mechanism evades the standardized system of HTML5\. Rather than promoting the use of standards, they promote the use of a proprietary and nonstandard signed zip package.

As they're "packaged", they aren't really "true" web apps, because they don't actually operate in the scope of the web. They are much closer to desktop apps, practically. They have no URLs, and thus can't be linked to, evading the very first two letters in HTML and HTTP: "HyperText". One of the greatest things about web sites is that they can be linked to, and they almost always share that universal identifier to share with people. It's universally accessible and one of the few things that actually enables intra-site interoperability.

## Conclusion.

While the "glorified bookmark" class of applications, which make up the vast majority of the Chrome Web Store, can be quite easily fixed by implementing something akin to the iPhone OS home screen web apps, the "packaged applications" are a bit more interesting. They are the source of that problem which the applications system was meant to resolve: permissions. In the current state, there is no system for handling multiple permissions on the web, aside from flooding the screen with infobars, when even that only partially works. What the web needs is a user friendly, informative, and useful system for giving additional permissions to web sites.

Along with that, the Web Store handles the selling of applications. Accepting money is a two part process, consisting of authentication and payment. Browsers should handle user identity, since they have the resources to do it right, in a nuanced, secure, efficient and user friendly way. Once that's done, payment would be a logical extension to that. A developer could drop in a Google Checkout widget to have one-click in-app-purchases by tying into the secure browser identity system.

The Chrome Web Store should be reduced to a community maintained directory of useful web applications, something like a wiki, and there shouldn't be a $5 fee to add applications.

Some people have expressed the idea that the Chrome Web Store is useful because it allows Google, a trusted party, to take down dangerous or malicious applications quickly. And while this is true, note that the Web Store is not actually the sole means to install chrome applications, and a malicious party would most likely exploit those alternate channels, and the only way to combat those is to institute a sort of Kill Switch, much like the kind that iOS, Kindle, and Android already implement.
<div><span style="color: #221122; font-family: 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Lucida, Arial, Helvetica, sans-serif; line-height: normal;">` `</span></div>
