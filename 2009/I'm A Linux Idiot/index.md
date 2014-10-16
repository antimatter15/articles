---
title: I'm A Linux Idiot
author: admin
date: 2009-01-04 12:10:10
categories:
  - Meta
tags: 
  - install
  - linux
  - phpMyAdmin
  - self deprecation
template: article.jade
---

So I needed to install phpMyAdmin, and having those epiphanies on how simple it is to install crap on Debian/Ubuntu, I typed in <tt>sudo apt-get install phpmyadmin</tt> and it worked fine. Mapped out all the dependencies, installed them all, and then popped up a nice user-friendly config window where you select which server to install it in.
![](lamp4.gif)
I had Apache2, so i just hit enter. Opened up my browser and went to /phpmyadmin. hmm. 404? tried /phpMyAdmin, and same.

So I googled it, and there were all these success stories. I went and tried <tt>sudo dpkg-reconfigure phpmyadmin</tt>, that same window popped up, this time i tabbed over to the ok button. and pressed enter. Checked again, still broken?

So i found [this guide](http://www.flyninja.net/linux/installing-apache-php-mysql-lamp-phpmyadmin-ubuntu-710-gutsy-gibbon), and it turns out you have to press space to select it -_-
