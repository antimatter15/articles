---
title: Distributed Torrent Search
author: admin
date: 2009-08-07 3:58:42
categories:
  - Ideas
tags:

template: article.jade
---

With the acquisition of The Pirate Bay, may people are now reexamining the flaws and central points of weaknesses in the BitTorrent protocol. While BitTorrent is functionally distributed, the applications don't discriminate and require all torrents to be tracked by tracker xyz, people all end up using the same tracker. Because when something is popular, people get the delusion that it's just better and use that for their torrents and just contribute to the delusion. What happens is that people end up all using a few select trackers and this totally non-ideal community formed issue is what causes these practical central points of weakness.

It's not just with trackers, but with many open protocols like XMPP and what Google Wave will become. Even though people can use any server and the functionality is equivalent, most people will end up using Google Talk or Google Wave as their server because everyone else is.

So I was just thinking, how would a Distributed torrent search system work? Well, I think it's fairly obvious to use some DHT to store the tracker files (which are pretty small usually). People could have a local copy of the entirety of the torrent list, and things could be updated though some decentralized push (XMPP-like?) system.

Well, for it to work, you need a sort of cache of torrent metadata within each user. One idea to protect people from from what is actually stored on their computers, is by using some hash or alternate vocabulary so that each peer's cache is searchable yet not decodable by the person who's machine contains the data.I think it would be ideal to seperate the networks which provide for search and those which give the actual torrent metadata, linked possibly by the info_hash value.
