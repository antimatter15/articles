---
title: my ideas for a browser os are coming true.
author: admin
date: 2009-10-08 3:33:55
categories:
  - Design
tags:
  - brower
  - chrome os
  - idea
  - os
template: article.jade
---

Yes, I know that the title is lowercase with a period in the end. It's totally strange and inconsistent but it _feels_ right.

Google's working on a notification API for Chrome. Chrome has a Pin Tab feature. Firefox has Faviconize Tab. Gears has a basic privledge escalation (not very fine grained yet). Firefox shows UAC-type privledge escalation for storing data and Geolocation.

To review the old post, this is how I think Chrome OS might work. All user facing applications (all apps other than the window manager, kernel, browser, should be user facing) should operate in Tabs. There are two types of tabs, "pinned" tabs and normal browsing tabs. Pinned tabs are automatically loaded when the user is logged in, are only a tiny icon, but are still always visible.

There will be a unified and consistent way for the user to voluntarily grant privledges to a web site that requests it. It won't be a catch-all i-totally-trust-this-app-to-every-bit-of-data-on-my-HDD sort of system that most operating systems use. It will be very fine grained, you can grant access to XHRs to a certain domain and huge warnings if the site requires access to the wildcard *. The privledges can extend from just accessing the notification API, cross domain XHR, geolocation, and **communicating with other tabs**. Communication with other tabs should be dome something like cross domain XHR, by allowing the user to grant a tab access to a certain domain/url. I would prefer the permissions dialog to be something less of a modal window that is employed by Gears or the little thing that pops up on the top for Firefox, and more of a icon that subtly appears somewhere that the user can click voluntarily. I think a UAC type stop-what-youre-doing-to-show-a-scary-message dialog is horrible and makes the user incapable of deciding intelligently. If there were a button which would make a box filled with checkboxes and a green/red gradient safety bar with messages, and educating the user that he or she really **does not have to give the site permissions**).

A typical application such as a mail notifier would be as follows

	<!doctype html>
	<html>
		<head>
			<script src="jquery.js"></script>
		</head>
		<body>
			<script>
				if(navigator.requestPermission){
					navigator.requestPermission("xhr","http://site.com/api.json")
					navigator.requestPermission("notify")
				}
				setInterval(function(){
					if(navigator.hasPermission && navigator.hasPermission("xhr","http://site.com/api.json" && navigator.hasPermission("notify")){
						$("#status").html("YAYNESS! You granted Awesomeness!").css("background-color","green")
						$.ajax("http://site.com/api.json", {user: $("#userid").val(), pass: $("#pass").val()}, function(data){
							$.each(data,function(message){
								notify(message.summary)
							})
						})
					}else{
						$("#status").html("no permissions!")
					}
				},1000);
			</script>
			<div id="status" style="background-color: red">No Permissions, please give me some super-powers?</div>
			<input id="userid" type="text" value="USERNAME" />
			<input id="pass" type="password" value="PASSWORD" />

			# Super Insanely Awesome Notifier!

			This is a super awesome notifier, if this doesnt work then you are an idiot or
			the internet isnt in the future yet. Here is where the about stuff and other stuff
			and stuffs that are stuffs can be put in! And if its not in the future, we all know
			the easiest way out is to blame microsoft for all our problems and say that at
			least google tried fixing our problems but it was all microsoft's fault.

		</body>
	<html>

The great thing about the thing above is that it gracefully degrades into a functionless web page if its not running in my imaginary super browser OS of the future. It's quite easy to make and requrires no API documentation (or at least for me since there's only 2 API calls and I just totally made them up). It's similar to the Jetpack and Chrome extensions idea in which the developer has little to learn for making an extension, but lowers the barrier even more: There's _nothing_ to learn. Whats above is just a _standard html5 web page with jQuery_. The only thing different is the hasPermission and requestPermission functions which don't exist so I made them up. It's not that it has anythign different, its just that the developer is thinking of the web page as a background process instead of _thinking_ of it as static content.

It's the same idea is Google Wave, it could be a Wiki, IM, or Email, all depending on how you _think_ about it.

For the permissions system, it really doesn't matter how it's implemented but it really has to eventually be done. The web is getting new abilities, and things like Geolocation, Local Storage, Offline SQL DB, Saving to disk, Reading files, and such all require special permissions (You wouldn't want any random site uploading your [SAM file](http://www.hackinthebox.org/modules.php?op=modload&amp;name=News&amp;file=article&amp;sid=5721&amp;mode=thread&amp;order=0&amp;thold=0) from your hard disk). Each of them have their own modal type dialog which queries the user if they want to grant the permission. Eventually, things like Audio from microphone, Video from webcam, cross-domain XHR,  and other peripherals like toasters get their own implementation, requiring special user granted permissions, an application may want 3 or more permissions simultaneously, it becomes very obvious a more consistent UI is needed for delegating these abilities.

For the interface, its easier for both users and developers. Developers dont need to do something like write complex xml manifests showing which location the file which shows the about text is and which one is the help. Here, you just have a web page that you put stuff in. Since the interface is the page. The tab/web page is a _unified_ Install Page, Help Page, About Dialog, Credits, Donation Box, everything, but _unified _(sure you could split it into multiple pages if you wanted like with any other web page)_._ Installing is just right-clicking on the tab and selecting the menu button that says "Pin Tab". If the application requires special privledges, the user can <span style="background-color: #ffffff;">click the icon which show you what the site wants, and you just check off whatever you feel the site deserves.</span>
