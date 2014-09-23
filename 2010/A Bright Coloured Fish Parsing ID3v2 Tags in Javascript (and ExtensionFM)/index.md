---
title: A Bright Coloured Fish Parsing ID3v2 Tags in Javascript (and ExtensionFM)
author: admin
date: 2010-07-10 2:34:31
tags: 
  - copyrightsucks
  - extensionfm
  - hacking
  - id3
  - js-id3v2
  - mp3
  - music
  - open source
template: article.jade
---

[![](250px-Ocellaris_clownfish.jpg "Stolen from wikipedia")](250px-Ocellaris_clownfish.jpg) Stolen from wikipedia

After having fun reinstalling [Ubuntu](http://www.ubuntu.com/desktop), only to get extremely bored by the newfound stability and familiarity of 10.04, I upgraded to the [Maverick Meerkat](http://www.ubuntu.com/testing/maverick/alpha2), where I was greeted by a [friendly GRUB error](http://www.google.com/search?q=grub_xputs+symbol+not+found&amp;qscrl=1). After consulting the Live CD a few times, I got into a normal desktop. Then I proceeded to install the two apps I ever use which aren't included in Ubuntu: [Chromium](http://www.chromium.org/) and [Shutter](http://shutter-project.org) (Maybe you could include [git](http://git-scm.com/) as well). After a bit of dismay as it seems Chromium _didn't_ sync extensions as advertised,  I proceeded to reinstall my extensions. At least the issue where I couldn't delete bookmarks was resolved.

It was also a neat opportunity to try out some new things, one of them was [Neat Bookmarks](https://chrome.google.com/extensions/detail/nnancliccjabjjmipbpjkfbijifaainp) after finding out that --bookmark-menu didn't work (I only found it ever existed when it was announced that it was removed, though), which has a far prettier icon than some other bookmarks menu addon I had previously.

Another extension I tried out was [Extension.FM](https://chrome.google.com/extensions/detail/ehohhddamheegbbkabfgegbaeminghlb). I've heard of it a while ago, but I never actually installed it for some reason, and there was a[ post on Ajaxian](http://ajaxian.com/archives/extensionfm-a-case-study-on-a-sexy-app-turn-extension) on it recently so I decided to try it out. The interface was neat (I knew that beforehand). I have an interesting (maybe not so much), system for storing my music on a local networked server (in my basement). So I went to it's apache URL and browsed to the file location. ExtensionFM loaded it all and stuck it into my library (as advertised), but all the cover art, song name, album name and artist information was missing! Oh noes! Obviously it was missing[ ID3 data](http://en.wikipedia.org/wiki/ID3).

The great thing about Chrome, Firefox and Greasemonkey extensions, is that the source code is practically open to anyone who uses it. View source or otherwise, you can always get at it and hack stuff to make things right (ignoring the legal implications that ruin innovation). Some people think that there needs to be more done to secure the author's source code from the user's prying eyes, but that could not be further from the case. Hopefully this will be a case for why the source code should be exposed to the user.

So, after finding the location, which wasn't the easiest thing as Chrome gives them these folder names based on a random generated public key which gives *no* hint on what the contents are. But as I only had a few plugins, getting ~/.config/chromium/Default/Extensions/ehohhddamheegbbkabfgegbaeminghlb/1.4.9_0/js wasn't too hard. I found sound-parser.js and looked a little into it, and lo and behold, no ID3 parsing!

That's probably expected as ID3v2 is a binary format, and JS was never that great at handling binary. I knew that there was an [ID3v1 parser](http://nihilogic.dk/labs/id3/). But I wasn't aware of an ID3v2 parser at the time, it seems that[ there is one](http://github.com/aadsm/JavaScript-ID3-Reader) that a quick google search would have saved me hours yesterday. So after [implementing the spec](http://www.id3.org/id3v2.4.0-frames), and googling several times why Picture Type $11 is "A bright coloured fish", I hacked it onto song-parser.js and through[ means detailed here](http://support.extension.fm/forums/59119-product-ideas/suggestions/897137-id3v2-data-patch), I got ID3v2 support in ExtensionFM. So yay, now what was missing: cover art, album name, song title and artist now all work :)

Anyway, the project for the ID3v2 parser (mine, the one you _shouldn't_ use), is on github at [http://github.com/antimatter15/js-id3v2](http://github.com/antimatter15/js-id3v2). If you want a neat little online demo, just go to the URL below. I wouldn't suggest any browser other than the Chromium nightlies or possibly Firefox 4.0 to view it as it relies on multi-file input and FileReader. Basically, this is how you use it: Press &lt;Browse&gt; and multi-select all the music that you have, and automagically, it reads it and parses ID3v2 data (all locally, mind you, so your secret collection of pirated music is not going to be sent to me for forwarding to the RIAA of your jurisdiction). It's then shown at a 5 second slideshow. Cover art (if not present in the song) is of a probably copyright-infringing image of a sad fish that google referred me to because of this interesting fish theme.

[http://antimatter15.com/misc/js-id3v2/id3v2.html](http://antimatter15.com/misc/js-id3v2/id3v2.html) &lt;-- Live Demo, you probably want to click it if you tl;dr'd this whole post.
