---
title: "Things that I haven't finished, and/or things I need to write posts about after I fix this blog"
author: admin
short: Open Gestalts
date: 2015-07-01 3:35:01
categories:
  - Capacitive Fingerprints

tags:
  - draft
template: article.jade
---

"We are stuck with technology when what we really want is just stuff that works." — Douglas Adams

To paraphrase Will Wright, your software doesn't just run on the computer -- it also runs in each of your users' heads.

No one has a monopoly on good ideas.


* Things which I haven't blogged about yet
  * CSS3 Boggle / Scramble
  * bzip2.js
  * Protobowl
  * Fafnir
  * Youtube Repeat
  * Wordlist
  * BOA: OAB parser in python
  * Chromecorder / Sprite Codec
  * Unidecode
  * Project Waldo
  * Syllable Counter
  * dist-sample-js
  * Anesidora Hack
  * Autocircle
  * Speed
  * Facebook Grapher
  * Pyrite — not yet finished
  * Recursion Poster
  * Coitometer / Alarm Clock
  * Laser stage lighting and stuff
  * Bookbinding


* CSS3 Boggle — backlogged from 3 years ago

* Desktop Automation / Macros

* Schlieren Optics
	* Think about stuff to do with these
	* Perhaps a glider which only has a rudder to stay afloat by navigating microweather
	* Where the wind is all tracked with computed tomography schlieren optics
	* Similar to "Refraction Wiggles for Measuring Fluid Depth and Velocity from Video"
		* http://people.csail.mit.edu/tfxue/

* TODO: think about signalling and goodhart's law vis academic testing

* Reinventing Programming
	* And as a subscript, reinventing the command line interface
	* Inspiration from calculators (Calca, Soulver)


* Rethinking the terminal
	* Something like IPython as a base
		* Consider designing/contributing a new interface for IPython
	* A triggering mode inspired by oscilloscopes
		* Recognize patterns in the output (markers/delimiters spanning an entire line, or certain text prefixes that repeat)
		* Create an interactive interface showing the most recent such region, and automatically figure out numerical values and then graph them.
		* Principle: Design for the lowest common denominator (Postel's law in action)
	* What level of the stack does this run on?


* Redesigning a web brwoser
	* Predictive back and forward buttons
	* Integrating history and the tab bar



* Zoomable browser history (learning browsing topics)

* Zoomable text editor
	* When we think of zoom, we usually think of something as boring as changing the size of things
	* That's a very physical-medium printed-paper sort of mentality that we should really start getting beyond
	* Because zooming isn't about the content density, it's about the content scale. And spatial scale is something quite different than mere zooming— because the important thing about spatial scale is that you at any particular scale, you're seeing the *same amount* modulated only by the altitude.
	* So instead of naively projecting text onto different size, we should think about what text actually means at different scales.
	* The most logical generalization of the concept of scale to text is summarization— I should have a document, where I can zoom out and see the rest of the document replaced with summaries of their contents.
	* But perhaps, this should be a foveated phenomenon, because in the context of a text editor, you still want to preserve local context (in large part because you really can't summarize text in-process), but the larger context is what kind of fades away
	* In the context of computer programming, this is similar to code folding (code blocks are condensed into their headers)

* Zoomable text browsing
	* This is essentially what a zooming user interface is, but perhaps a little less ridiculous
	* Constrain navigation to 1 dimension (because two is just 2 much)
		* Scroll

* Reviving Enso
	* Launcher: Essentially Alfred or that mac thing
	* Words: Universal spell check
	* TeXAnywhere: Embed LaTeX anywhere
	*

* Music Visualization
	* LiFx something
		* What exactly did I do vis lifx?
	* Oh yeah, that thing with quartz composer piping things into things

* Eulerian Video Magnification
	* That thing is pretty cool

* Schedule Compare 2
	* Such ReactJS
	* Also, gotta love esoteric stacks with icedcoffeescript

* Icosahedron
	* Talk about its inception
	* Spinning in perpetuity
	* Make pretty gifs and shit

* Capacitive Fingerprinting
	* Finish hacking the OS X touch driver
	* Create something with arduino which can send capacitive signals
	* Something with that capacitive meter from sparkfun that I bought
		* https://www.sparkfun.com/products/9485
	* Contact synaptics mayhaps
	* Maybe build some sort of demo to show off to other people

* Spectre
	* The utv007 driver type thing in python that I built yesterday
	* Obligatory james bond pun thing

* Pedestrian
	* Finish that script and record the net flux of nextees over a 24 hour period
	* Create some visualizations for when people walk in and out

* Etekcity
	* Robert's SDR, Mathemath, and comparison to that other guy's thing
		* http://www.msilverman.me/2014/01/interfacing-with-remote-controlled-outlets/
		* http://hackaday.com/2012/06/05/home-automation-with-rc-wall-plugs-and-raspberry-pi/

	* I bought this
		* http://slickdeals.net/f/7507730-5-pack-etekcity-wireless-remote-control-outlet-light-switch-w-2-remotes-21-50
	* TODO: learn more about home automation
		* what is ioio https://github.com/ytai/ioio/wiki
		* what are ninjablocks
		* http://samy.pl/keysweeper/

* Weather Monitoring with Arduino
	* Build a data visualization frontend for Sparkfun's phant

* New Protobowl Packets Editor
	* Edit packets and shit
	* Write blog post about this
	* Respond to emails about things

* Embed application state in the rendering of an application (steganographically)
	* Load that state from accessing screenshots.
	* Some plugin for the image rendering routines to check (a la naptha)
	* Something should be translation invariant


* Naptha
	* API for embedding into websites
		* monetization?
	* Launch translation support
		* monetization?
	* Exemplar driven editing
	* Firefox + Opera + Safari

* HCI Asymmetries
	* What are technical limitations on how we interact with certain forms of content (i.e. how do we come up with more things like naptha?)
	* What are quasi-opaque media?
		* Images/Photographs
			* Screenshots
			* Pictures of animals
			* Pictures of reciepts
			* Scans of documents
			* Pictures of places
			* Stills from films
			* Equations (LaTeX rendering)
		* Video/GIFs
			* Snippets from longer form (Film/TV Show/Video)
			* Animations of mechanisms
		* Audio
			* Conversations
			* Audio tracks from video
			* Sounds from background or of particular events
	* What are examples of transparent media? (in particular, media acting in such a way which enables a sort of interaction)
		* Documents
			* Highlighting
			* Copying
			* Pasting
			* Searching for occurances
			* Translating
		* Photographs
			* Removing objects (watermarks, tourists, enemies)
			* Adding objects
			* Adding text
			* Searching for duplicates/variants (tracing provenance)
		* Movies
			* Identifying actors/objects in a scene
			* Identifying the source

* Another way of organizing this is to look at contemporary primitive media, examine their particular applications, and the uses which they may benefit from, and then figuring out a way to specialize

	* Video
		* Online Education & Video Lectures
			* View closed captions
			* Search through lecture videos by concept
			* Densely summarize events
			* Correlate displayed regions with speech
			* Variable speed for optimizing content absorption rate
			* Community annotation and commenting (for instance, to rectify some factual error)
			* Electroencephalograph to aid comprehension/understanding/avoid boredom/mainaining acuity
			* Spaced repetition in the form of video lectures (this is pretty interesting, and a cursory google looks like it's not really explored)
		* Film / TV
			* Identifying actors
			* Identifying objects
			* Identifying scenes (locations)
			* Tracing allusions, metaphors or references (link director's commentary)
			* Connecting story arcs
			* Community annotations and comments (highlighting particular artistic decisions)
			* Community cuts (a la Topher Grace's splicing of Star Wars) for remix culture (new stories, etc)
				* Alternatively, computer-generated cuts based on learning algorithms trained to generate cuts with particular heuristc features
			* Watching summaries of a film (esp. inline recap for pertinent story arcs)
			* A new form of film which lacks a canonical telling, where in a manner similar to Echonest's infinite jukebox, you can have a movie which looks different (perhaps even telling a different story)
			* Make lip movement agree with dubbed voices
			* Find out where you are without knowing how far along you are, and identify where you are in the movie without exposing yourself to spoilers
			* Video statistics (how many seconds on average take)
			* Spaced repetition of house episodes to make sure I don't forget the fact that I've watched every episode
		* Vlogging
			* Automatic summarization and clustering
			* Jumping between commentators for a pseudo-conversation
			* Skipping through sections that cover content that's already been convered
		* News
			* Annotations
			* Tickers
			* Live Polling
			* Content source aggregation and viewpoint deduplication
	* Text
		* Encyclopedia / Lecture Notes
			* Lookup definition of a word
			* Interact with numeric computation and diagrams
			* Probabilistic model of browsing history with estimation of specific sentences/paragraphs that have been read
			* Skipping to parts of interest (cued by search information or behavioral history)
			* Highlighting the edit history of the article
			*

		* Document
			* Lookup word definition
			* Replace word with synonym
			* Translate body of text
			* Embed graphics
			* Embed maps, surveys

		* Chat / Conversation
			* Search history of conversation
			* Share current location / embed map
			*
	* Images
		* Photographs
		* Diagrams / Technical Illustrations
		* Illustrations / Paintings
		* Screenshots



* Ocrad.js
	* Write blog post about new release
	* Update demos
	* Perhaps integrate SWT
		* Rewrite SWT and put that in a new library?
		* SWT with component filtering

* Inpaint.js
	* Investigate incorporating PatchMatch algorithm
	* Create nice demo and blog post about it

* Phash.js
	* Create a demo for identifying memes
	* Use optical flow to do image registration (or otherwise) to inpaint
		* Perhaps use laplacian blending or color correction
		* Perhaps combine with inpaint.js


* Ocracy
	* I should really get this to work
	* Perhaps use recurrent neural nets because rnnlib exists
	* Experiment with RNNlib

* Automatic Cinemagraph Generator
	* /r/perfectloops

* On Jan 12, I fucked up my computer
	* was installing haskell, so it all started innocuously enough
	* there was some dylib issues
	* things started being weird so i tried turning it off and turning it on again
	* it wouldn't turn on
	* walp
	* found out the recovery mode Cmd+R thing
	* copied the /System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib file
	* crossed fingers and rebooted
	* it turned on
	* but spotify would crash on load
	* file /Applications/Spotify.app/Contents/MacOS/Spotify
	`/Applications/Spotify.app/Contents/MacOS/Spotify: Mach-O executable i386`
	* hmm..
	* file /System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib
	`/System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib: Mach-O 64-bit dynamically linked shared library x86_64`
	* merp
	* downloads yosemite from app store
	* Install OS X Yosemite.app -> Contents -> SharedSupport -> InstallESD.dmg
		* Packages -> BaseSystemBinaries.pkg
	* file /System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib

		/System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib: Mach-O universal binary with 3 architectures
		/System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib (for architecture x86_64):	Mach-O 64-bit dynamically linked shared library x86_64
		/System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib (for architecture i386):	Mach-O dynamically linked shared library i386
		/System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/ImageIO.framework/Versions/A/Resources/libPng.dylib (for architecture x86_64h):	Mach-O 64-bit dynamically linked shared library x86_64

	* For some reason I couldn't move things to trash, and some menu bars had the wrong icons
	* On Jan 13, I rebooted my computer and it couldn't find the operating system
	* I opened up recovery mode and reinstalled yosemite through its online/remote boot or whatever
	* It was stuck at 2 min remaining for 3 hours
		* turns out that's a known issue for people who use homebrew/MacTeX which install lots of things in /usr/local
	* It's okay now.



I guess for quite a long time I've been looking for the right words to describe my current state, and I think I might have found them— delusions of grandeur. I've always been kind of self deprecating— my blog's description originally, and still, refers to itself as "a place to talk about ideas and stuff like everyone else". The problem is that I've noticed, is that even though it's something I still say regularly, it's no longer something I believe. In its place, there is something far more sinister, and that's a delusion of grandeur.

Existing in the nexus of things that lie on the verge of technical tractability and the potential to enrich human experience.








Time.

It's 2:46am on January 24th. For me, it's Friday night. For you, it probably depends on what your time zone is. I just finished watching the cinematic cutscenes for Ratchet and Clank: Into the Nexus and Ratchet and Clank: A Crack in Time (Which in high school, I affectionately referred to among friends as "R.C. FACKIT").

In particular, it I was watching some YouTube videos (I was trying to find evidence for self-reference as a trite means for escaping writer's block— which, if you've read any parentheticals in this blog, yes, including this one, is a technique I'm rather intimately familiar with) when I had stumbled on a related link with the trailer for an upcoming Ratchet and Clank animated film.

Ratchet and Clank is my favorite video game series. Oddly enough, that's one of the few statements about my own self identity that I'm totally comfortable with. I won't really argue about it's intrinsic merits, because I'm not a gamer and I really haven't sampled the broad gamut of the medium enough to make any sort of objective assessment. Ratchet and Clank is my favorite game because it's almost definitive for me— I was a pretty small child when I was first introduced to the first installment, and I've made an attempt to play every sequel to it. The series has evolved, but engaging with the franchise is almost a pacemaker to my own recollection of time.

But it's something I've grown out of, and that's not necessarily something I'm proud of. It's a strange feeling— seeing the memento of a past life— one that you know is unquestionably yours, but one that you aren't living anymore. And it begs the question: "what happened?". Tautologically, the answer is pretty ironic— "life".

I learned in short order, that in these intervening years came the publication of a new fourth and final game to the Ratchet and Clank: Future mini-franchise. Ratchet and Clank: Into the Nexus, as it's called. And with the like ESPN or something that Google has, lo and behold, the ripped "HD Cutscenes Ratchet and Clank Nexus" was suggested in that ever-distracting sidebar.

It was just before midnight that I hit play, and I watched it all. I heard the names of the characters— part of a canon long forgotten. I felt the starved despairation of a cache miss of the mind every time it alluded to a past plot element. That, and the fact that it just wasn't that good. The plot was just sort of empty and meaningless, shallow and full of holes. It cast my entire memory of the series into question— perhaps since my wisened self sees the emptiness of this game, all the emotional depth was all part of some temporal scaling fallacy.

Yearning for some sort of redemption, I made another click and committed the next hour and half of my life to reliving a cherished bit of nostalgia: "Ratchet & Clank Future: A Crack In Time Cutscenes With Subtitles HD".
