---
title: Raspberry Pi
author: admin
date: 2012-08-14 11:00:26
categories:
  - Hardware
  - Raspberry Pi
tags: 
  - arduino
  - arm
  - buying
  - crt
  - dvi
  - facebook
  - hdmi
  - lilypad
  - linux
  - megaton
  - money
  - near future
  - node
  - npm
  - paying
  - paypal
  - performance
  - raspberry
  - speed
  - stuff
  - touchpad
template: article.jade
---

[![](Raspi_Colour_R-248x300.png "Raspi_Colour_R")](Raspi_Colour_R.png)As part of the shift between long multi-kiloword blog posts which are somewhat more like press releases back into a sort of more personal (i.e. blog-esque) format, I guess I'll talk about my newly-arrived [Raspberry Pi](http://en.wikipedia.org/wiki/Raspberry_Pi). Right now, there isn't terribly much to talk about since I've only had it for about two weeks.

I've been planning on getting a Raspberry Pi for a pretty long time, and I was actually pretty excited about that. For the weeks preceding the official announcement, I built a tiny script which ran in a ten-minutely cron job which would basically download the purported Raspberry Pi store (raspberrypi.com, note the dot-com rather than dot-org, which their homepage is situated at) and compare the hash, notifying me via Ubuntu's built in notification system.

On that sleepless night when the actual pre-sale announcement was being made, I was incessantly checking [raspberrypi.com](http://raspberrypi.com), which had suddenly morphed into a server maintenance message (which remains to this very day). The anticipation was intense, and some twenty minutes after it was supposed to happen was when I realized that the whole time I had been checking the wrong page. The announcement came instead on [raspberrypi.org](http://www.raspberrypi.org/), their main blog, and by that time, it was certain that all the distributor's sites were already collapsing under the crushing load of a million souls crying out for a taste of berry-scented silicon pastry.

On the next day, I checked the sites again, and all the order pages were already closed. Either way, it wasn't terribly useful for me because most of them didn't support Paypal. Fast forward a veritable eternity, on June 16th, I was notified via email that RS Components that I would be allowed to order the device some time[ in the near future](http://uk.rs-online.com/web/generalDisplay.html?id=raspberrypi&amp;file=questions#Queue). Sure enough, on the 22nd, another email gave me a link to the order form, which I promptly filled out and I began the process of waiting. Not really, since I had other stuff to do and most of my interest had already vaporized at the daunting 7 weeks it was supposed to take.

Another eternity later, it arrived in some rather nice packaging. It actually came as a bit of a surprise, because I had become so accustomed to waiting that I had never really expected it to materialize so suddenly. But when it did, it was everything I imagined and more. It came in this rather nice cardboard box, which I eventually cut in half with an X-Acto knife (which nowadays, I use for all my paper splicing needs) to build a makeshift case. I fumbled around in a closet and found a neglected 16GB SD card (probably back from the era when point-and-shoots were actually preferable to mobile phones) and installed that weird Debian distro (after having a little internal debate on what to install). But the first thing I had done was plugged it into a monitor through a HDMI-to-DVI converter. I took the charger from my Galaxy Nexus (I wasn't using it for anything since I charge it in my room from my HP Touchpad Charger, and my Touchpad idly draining power from a cool inductive stand, the standardization of chargers is really pretty awesome), and used that as my Pi's permanent power supply.

I also had a 2000mAh LiPo battery which I was going to use with my Arduino LilyPad for some cool foot-operated telegraph which I wanted to use as essentially a UPS for the Pi, but a bit of googling reveals that that might possibly entail actual electronicswork, so maybe that's something for later.

I turned it on, and lo and behold it didn't work. I actually never quite figured out why. Then, I tried plugging it into a really old 13 megaton CRT TV, which makes me realize how it's sort of weird that the unit of megatons is hardly ever used for things other than atomic weapons, and now it feels oddly inappropriate for a hyperbole for the mass of a TV, but maybe it's actually sort of appropriate because CRTs are _terrifying_. So analog seemed to work, except for this problem where my keyboard would keep repeating letters and not working well. That wasn't a good start.

But after a little googling from my Chromebook, it turns out the keyboard issues came from the fact that I had plugged in my only spare USB keyboard which happened to be a Logitech Mouse+Keyboard+Speaker thing and my teensy Galaxy Nexus charger couldn't eke out enough watts to power it. And the issue with the HDMI-to-DVI thing was just because I needed to restart with the cable plugged in. But neither of them posed a real material issue because I had been intending to use it as a headless rig from the start.

The first thing I really noticed was how surprisingly easy it was to install things. I had expected the ARM repositories to basically lack everything which might be useful, but it turns out that actually almost everything I wanted was available. I didn't dare compiling anything, but [Node](http://nodejs.org/) (albeit a somewhat old version) was available from the repos, so I never really needed to. I had to manually update to a new version of [npm](https://npmjs.org/), but that wasn't that bad. I set up [forever](https://github.com/nodejitsu/forever/) to run a few apps, but not much.

One of the main reasons I could justify getting the Raspberry Pi however, was to run my [Facebook logging script](http://antimatter15.com/wp/2012/05/visualizing-facebook-activity/) on something other than my main computer, and aside from getting confused trying to use sendxmpp, it was fairly straightforward.
