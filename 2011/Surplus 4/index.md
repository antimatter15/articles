---
title: Surplus 4
author: admin
date: 2011-10-29 2:48:42
tags: 
  - add
  - chrome
  - extension
  - google
  - google plus
  - plus
  - popular
  - rewrite
  - sold to the highest bidder
  - surplus
  - update
  - version
template: article.jade
---

[![](Screenshot-at-2011-10-28-213821.png "Blurry")](Screenshot-at-2011-10-28-213821.png)

Recently Surplus stopped working. Well, it hasn't been working for a lot of people for a long time already, but that's besides the point. It stopped working entirely. Surplus has always been a rather fragile creature. It operates like a kid on a high speed scooter attempting to carry a house of cards between two strangers. That house of cards is part of a delicate system of frames inside frames inside frames inside frames that move between frames. Surplus is this fairly atrocious mess of frames.

Framing things works out fine until you discover that whatever you're framing is trying to break out. Meet the X-Frame-Options header, the source Surplus's recent predicament. It has well meaning motives: to prevent Google from suffering from evil attacks like Clickjacking, XSRF and other nasty things. Incidentally, security-wise, Surplus would probably belong closer to something of that nature than a legitimate application. It doesn't use an API because applications generally wouldn't find it useful.

Recently, all Google properties started including that X-Frame-Options header, and now can't be embedded in frames. It wasn't an absolutely unprecedented move, because just a few weeks earlier Google Video had started sending out the header (which led to an update which moved from a Google Video host frame). But now it was across all Google Sites, and there was no short term hack that could be done.

The solution was to take a random Google page which didn't send out the header and mimic all the postMessage messages that are sent from the Google Plus notifications frame. Consequently, the entire frame signaling and attachment system had to be rewritten, and that system was so deeply tied into everything else that Surplus 4 ended up being almost an entire rewrite (the inner frame actions, the options page and the notifications parser did not change).

[https://chrome.google.com/webstore/detail/pfphgaimeghgekhncbkfblhdhfaiaipf](https://chrome.google.com/webstore/detail/pfphgaimeghgekhncbkfblhdhfaiaipf)
