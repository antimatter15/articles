---
title: Adsense Notifier under Firefox 3
author: admin
date: 2008-12-16 9:54:19
categories:
  - Uncategorized
tags: 

template: article.jade
---

So there's this awesome plugin called Adsense Notifier, but it doesn't work on the latest firefox version, though it installs fine.

well, i've never delved into the inner workings of firefox before, so this is probably really really crude and over-complex.

I, armed with the mighty firebug went to about:config to experiment with random code. I eventually got to this folowing code which adds the missing entry to the passwords in firefox.

I put my username where it says INSERT USERNAME HERE (obviously).

I went to about:config, 
var url = "chrome://adsense/";
var myLoginManager = Components.classes[ "@mozilla.org/login-manager;1" ].getService( Components.interfaces.nsILoginManager );
var nsLoginInfo = new Components.Constructor( "@mozilla.org/login-manager/loginInfo;1", Components.interfaces.nsILoginInfo, "init" );
var newLogin = new nsLoginInfo( url, url, null, "INSERT USERNAME HERE", "stuff", "", "" )
myLoginManager.addLogin(newLogin)

then i just went throuh the adsense notifier friendly GUI and set the username and passowrd
