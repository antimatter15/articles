---
title: The Ambiguity of "Open" and VP8 vs. H.264
author: admin
date: 2011-01-13 5:38:27
categories:
  - VP8 vs. H.264
tags: 
  - avc
  - constitution
  - evil
  - google
  - h.264
  - hevc
  - history
  - long post
  - mpeg
  - ogg
  - openness
  - sorenson spark
  - standardization
  - the medium is the message
  - theora
  - video
  - vp6
  - vp8
  - webm
template: article.jade
---

Google has recently announced their intention to [remove the H.264](http://blog.chromium.org/2011/01/html-video-codec-support-in-chrome.html) video codec from its Chrome browser. This decision has been smeared as an evil campaign for controlling video on the web, akin to [not-invented-here](http://en.wikipedia.org/wiki/Not_Invented_Here) syndrome. It's also been lauded as the push that the web needs to[ remain open ](http://www.osnews.com/story/24245/10_Questions_for_John_Gruber_Regarding_H_264_WebM)and free.[ Mostly, it's been marked as inconsistent,](http://daringfireball.net/2011/01/simple_questions) due to the bundling of Adobe's proprietary Flash player.

Richard Stallman [doesn't like the term Open Source](http://www.gnu.org/philosophy/open-source-misses-the-point.html) because it fails to embody the true meaning of "free software", and the one thing that's worse is the word "open". This debate can't simply be labeled as one for or against openness (even ignoring the technical details).

H.264 is an open standard. It was developed by a committee, standardized, reviewed by many engineers and developers for multiple companies and has been standardized for use with a multitude of containers and devices. However, H.264 is not royalty free. Software patents in many countries restrict the distribution of software that utilizes the codec to those who pay the MPEG-LA.

VP8 is not a standard. It was developed secretly by a single company, and until recently, had only a single working implementation. The public wasn't open to collaboration on the specification until the bitstream spec was frozen, including the bugs that existed within. Now, the source code and reference implementation are available under liberal licenses, and all the related patents are irrevocably royalty-free.

Adobe Flash, while not synonymous with a video codec (unless you mean .flv flash videos, which are either VP6 or Sorenson Spark), is going here anyway because everyone feels like comparing it. Flash's SWF format is not standard, but it is open. There are a few implementations (Swfdec, Gnash, GameSWF, Gordon, etc), but none of them are as complete as the official proprietary implementation. There's a [bitstream specification](http://www.adobe.com/content/dam/Adobe/en/devnet/swf/pdf/swf_file_format_spec_v10.pdf) that anyone can read to create an independent implementation of the player. Implementing and using the Flash player is still royalty-free (Since the Flash VM can decode H.264, obviously that part, not controlled by Adobe still has royalties), anyone can make software that can export SWF animations without paying Adobe.

## Implementation vs. Distribution

#### Or: How Bundling Flash doesn't violate the [Novikov self-consistency principle](http://en.wikipedia.org/wiki/Novikov_self-consistency_principle)

<table>
<tbody>
<tr>
<th>Name</th>
<th>Standardization</th>
<th>Implementation</th>
<th>Distribution</th>
<th>Dev History</th>
</tr>
<tr>
<td>**Theora**</td>
<td style="background-color: #ffff00;">Standardized?</td>
<td style="background-color: #99cc00;">Open Source</td>
<td style="background-color: #99cc00;">Royalty Free</td>
<td style="background-color: #99cc00;">Mostly Open</td>
</tr>
<tr>
<td>**VP8**</td>
<td style="background-color: #ff9999;">Not Standardized</td>
<td style="background-color: #99cc00;">Open Source</td>
<td style="background-color: #99cc00;">Royalty Free</td>
<td style="background-color: #ffff00;">Mixed</td>
</tr>
<tr>
<td>**H.264**</td>
<td style="background-color: #99cc00;">Standardized</td>
<td style="background-color: #99cc00;">Open Source</td>
<td style="background-color: #ff9999;">Royalties</td>
<td style="background-color: #99cc00;">Open</td>
</tr>
<tr>
<td>**Flash***</td>
<td style="background-color: #ff9999;">Not Standardized</td>
<td style="background-color: #ff9999;">Proprietary</td>
<td style="background-color: #99cc00;">Royalty Free</td>
<td style="background-color: #ff9999;">Proprietary</td>
</tr>
</tbody>
</table>
_* Adobe Flash isn't a video codec_

Each column of the chart can be treated as one part of "open". The &lt;video&gt; debate now primarily concerns VP8 and H.264, as Theora is inferior for technical reasons and Flash isn't a video codec. I don't know if Theora's actually standardized, but it has multiple implementations and was developed by the Xiph.Org foundation, and is the closest thing to an actual standard, short of being a product of MPEG. Theora was created from On2's VP3 code, but was changed significantly by the Xiph.org Foundation before release, so the development history can be considered mostly open. VP8 as announced, and the bitstream was frozen shortly afterwards, leaving little community involvement. For the years before its debut as part of WebM, the format was secret, patent encumbered, and proprietary. At least now, the source code is open and people are free to do whatever they please, but the open source video community probably had very little say in the development of the codec. H.264 has an open software reference implementation, as does VP8 and Theora. Flash's de-facto implementation is Adobe's, which is proprietary.

The one that concerns Mozilla, Opera and Google is the distribution rights; whether or not royalties have to be paid. Notably, this is where the parallel drawn by most critics of Google's move with H.264 and Flash comes into question. Many people believe that Flash is the epitome of evil, and proprietary software, and embodies everything wrong with proprietary software. The distribution column is arguably the most important, and it's the one that fundamentally determines whether or not something acts as a detriment to "open innovation". Flash animations and applications can be created and distributed without paying royalty fees to Adobe, regardless of the viewership. Innovation is still permitted as long as the distribution is free (except with changing the inner workings of the proprietary implementation).

## The Ambiguity of "Plugin"

#### TODO: Use this subtitle to mention random tangential thoughts.

It seems there are lots of misconceptions about WebM, and new ones as well, because of the use of the word "plugin" by Google in their "[More about Chrome HTML Codec Change](http://blog.chromium.org/2011/01/more-about-chrome-html-video-codec.html)". Here's what the relevant part of the post says (it's buried into the last paragraph).
> This is why we're joining others in the community to invest in WebM and encouraging every browser vendor to adopt it for the emerging HTML video platform (the WebM Project team will **soon release plugins** that enable WebM support in Safari and IE9 via the HTML standard &lt;video&gt; tag).
Microsoft and Apple through IE9 and Safari, respectively, rely on the underlying operating system's multimedia frameworks to handle &lt;video&gt; decoding. Chrome and Chromium bundle a customized version of the ffmpeg framework, while Opera uses gstreamer and Firefox has its own framework built on various open source codec libraries.
<table>
<tbody>
<tr>
<th>Browser</th>
<th>WebM</th>
<th>H.264</th>
<th>Theora</th>
<th>Anything Imaginable</th>
</tr>
<tr>
<td>**Firefox**</td>
<td style="background-color: #99cc00;">Version 4</td>
<td style="background-color: #ff9999;">Never</td>
<td style="background-color: #99cc00;">Version 3.5</td>
<td style="background-color: #ff9999;">Never</td>
</tr>
<tr>
<td>**Chrome**</td>
<td style="background-color: #99cc00;">Version 6</td>
<td style="background-color: #ff9999;">Removed in Version 10</td>
<td style="background-color: #99cc00;">Version 3</td>
<td style="background-color: #ff9999;">Never</td>
</tr>
<tr>
<td>**Opera**</td>
<td style="background-color: #99cc00;">Version 10.60</td>
<td style="background-color: #ff9999;">Never</td>
<td style="background-color: #99cc00;">Version 10.50</td>
<td style="background-color: #ff9999;">Never</td>
</tr>
<tr>
<td>**Safari**</td>
<td style="background-color: #ffff00;">QuickTime</td>
<td style="background-color: #99cc00;">Default QuickTime</td>
<td style="background-color: #ffff00;">QuickTime</td>
<td style="background-color: #99cc00;">Default QuickTime*</td>
</tr>
<tr>
<td>**IE9**</td>
<td style="background-color: #ffff00;">Windows Media</td>
<td style="background-color: #99cc00;">Default Windows Media</td>
<td style="background-color: #ffff00;">Windows Media</td>
<td style="background-color: #99cc00;">Default Windows Media*</td>
</tr>
</tbody>
</table>
_* Well, not really *anything* imaginable, but a lot of them_

QuickTime and Windows Media are pluggable multimedia frameworks. And since Safari and IE9 use them for &lt;video&gt; support, any codec or container format supported by the respective frameworks, works in the browser. For QuickTime, the list for videos goes along the lines of 3GP, Apple Video, AVI, DV, Cinepak, H.261, H.262, H.263, H.264, Microsoft Video 1, MPEG-1, MPEG-4 Part 2, Motion JPEG, Pixlet, Planar RGB, Sorenson Video, Qtch, QuickTime Movie, and QuickTime VR. But these media frameworks are _pluggable_, which means they play whatever codecs are installed. It just happens that those codecs listed above are plugins that are installed _by default_, somewhat analogous to how Google Chrome bundles Flash. The plugin frameworks for multimedia don't treat plugins _any_ different from "native" codecs. There's absolutely no way to tell the difference from a user perspective. Right clicking a video will give you the same ordinary context menu.

Codec packs are often installed by users anyway. A codec pack consists of a set of plugins for the operating system's multimedia framework. Once one of those codecs are installed to the system, support is available to the applications that rely on the OS's framework: QuickTime Player, Windows Media Player, IE9 and Safari.

Notably absent are the Opera, Chrome and Firefox browsers that ignore whatever is installed, to use their own bundled decoders. There's a reason for this, and it's pretty easy to spot. Firefox, Chrome and Opera are also the only ones on the list that aren't tied to a specific operating system, and bundling your own media framework lets you keep the functionality consistent. IE and Safari aren't cross platform. Well, Safari works on Windows, but it still requires QuickTime for Windows to be installed to play the video content.

You also don't want all the other video codecs thrown into the mix. Standards are about _standardization_, where you have a limited number of codecs instead of an entire forest of them. This brings us to a bit of _History_, I'll begin with the olden days. I can't tell you too much, as much of the first section happened when I was 6 years old- and certainly wasn't into the negative user experience of platform-specific multimedia plugins.

## A Brief History of Stuff Named "A Brief History..."

#### Uh... I mean, Video on the Web.

Before the popularity of HTML5 Video, or event Flash, video was viewed on the web using the RealVideo, MPlayer, VLC, Windows Media Player, and Quicktime _Plugins_. Note that pretty little plugins aren't plugins to the underlying multimedia frameworks: these are the nasty type of plugins that Flash is among. They're the plugins that take a long time to load, have interfaces that never look like the surrounding page or browser, only work on certain operating systems, at best, inconsistently. This is the epitome of what standardization is meant to prevent, and the distillation of everything that's wrong with plugin based video.

Flash's popularity (probably thanks to YouTube), brought a semblance of _standardization_ to the industry. Video on the web was delivered through the flv container, encoded either with Sorenson Spark or, in later versions of Flash, On2's VP6\. A while later, H.264/AVC which was later added to Flash, and as the superior codec, most people switched to that and FLV is slowly fading away.

HTML5 video became popular recently. I'll say it's probably because of iOS, since that's the only way to get web video to play there and the rest of the aggressive marketing that Apple does. This brings us to _today _(or at least the general time period of early January 2011 in which I'm writing this post in). Google has just announced it's intention to remove H.264 from an upcoming revision of the Chrome browser (much like how the Chromium browser _never_ supported H.264). And everyone on the internet that cares enough to say a word is going insane. Which brings us back to the last section, about how Safari and IE9 use the operating system's underlying multimedia frameworks and how all the other browsers (Firefox/Chrome/Opera) that work on my beloved operating system (Linux) bundle their own.

If Firefox, Chrome and Opera used the OS's media frameworks, we would be set back into the dark ages when people used every video codec imaginable and nobody would be happy. Standards exist for _consistency_, and it would be terrible if people started to go on a cost saving measure to never again transcode video, and serve it straight from the server's filesystem as AVI files containing DV or god forbid MJPEG (the same format the users's uploaded!) because all the Safaris and IE9s could play it fine. The fact Firefox, Chrome and Opera bundle their own multimedia frameworks forbids the possibility of this, because those browsers (in the forseeable future) will _never_ support anything other than WebM, Theora and potentially H.264.

## There's more to H.264 than just H.264

#### This part doesn't make much sense.

Often, the argument against VP8 is that it's inferior to the H.264 codec, and to me, this seems like the most ideologically valid concern. But in a lot of cases, it stems from a misunderstanding of how H.264 works. H.264 is not a single video codec (not even to mention multimedia container formats), but rather has several _Profiles_ that work on different devices and implementations. Rarely are videos encoded only in MPEG-4/AVC H.264 Extended Profile at 1080p and 60fps. Go on the Apple store and you'll see that every iPod device you can find (including the iPhone), includes what video codecs are supported. And it doesn't just say H.264, but rather, something much more wordy like
> Video formats supported: H.264 video up to 720p, 30 frames per second, Main Profile level 3.1 with AAC-LC audio up to 160 Kbps, 48kHz, stereo audio in .m4v, .mp4, and .mov file formats
For the insanely great [iPhone 4](http://www.apple.com/iphone/specs.html). Google is meaner and doesn't make the information about profile support on the Nexus S quite as accessible (though it's not the only reason I'm an iPhone user), but it should be safe to assume it's something along the lines of what the iPhone 4 supports. The[ iPod Classic](http://www.apple.com/ipodclassic/specs.html) has a nice, even longer string, that represents even less support for H.264:
> H.264 video, up to 1.5 Mbps, 640 by 480 pixels, 30 frames per second, Low-Complexity version of the H.264 Baseline Profile with AAC-LC audio up to 160 Kbps, 48kHz, stereo audio in .m4v, .mp4, and .mov file formats; H.264 video, up to 2.5 Mbps, 640 by 480 pixels, 30 frames per second, Baseline Profile up to Level 3.0 with AAC-LC audio up to 160 Kbps, 48kHz, stereo audio in .m4v, .mp4, and .mov file formats;
This is because very few devices can actually utilize all the great features that H.264 defines. Wikipedia has [a nice pretty chart](http://en.wikipedia.org/wiki/H.264/MPEG-4_AVC#Profiles). So the point of all of this is to say, even though VP8 is inferior to H.264 from a purely technical standpoint, you probably can't just use the Main or Extended profiles to support all the devices that "support H.264". Does this invalidate the inferiority argument? Nope. Dark Shikari [said](http://x264dev.multimedia.cx/archives/377) "I expect VP8 to be more comparable to VC-1 or H.264 Baseline Profile than with H.264". But the large number of devices that support H.264 might actually only support the baseline profiles.

## My Hopeless Ideals

#### Better be blunt with what will probably never happen.

VP8 is a bit worse than H.264, and had it been a patent encumbered video format, there would be almost no reason to prefer it over AVC. The &lt;video&gt; part of the HTML5 specification states:
> It would be **helpful for interoperability if **all browsers could support the same codecs. However, there are no known codecs that satisfy all the current players: **we need a codec that is known to not require per-unit or per-distributor licensing**, that is **compatible with the open source** development model, that is of **sufficient quality** as to be usable, and that is not an additional **submarine patent** risk for large companies. This is an ongoing issue and this section will be updated once more information is available
The only major codecs that are royalty free are Theora and VP8, and the former probably isn't of sufficient quality. Both of them come with patent risks (or at least that's what MPEG-LA wants people to believe), leaving a set of zero acceptable codecs. For this to work at all, something needs to be compromised.

H.264 defines a baseline profile that all decoders could be reasonably expected to handle. Such a profile exists so that the video can be viewed, albeit with inferior compression on a variety of devices and platforms with limited computational ability. The internet was built on interoperability, and HTML5 needs an equivalent "baseline codec" for the web. Something that compresses video at sufficient, though not bleeding-edge quality. Something that can be implemented and distributed openly on all platforms.

For HTML5 &lt;audio&gt;, nearly all browsers implement the basic WAV codec. It serves as an acceptable baseline for small snippets of audio to be played in a cross-brower manner. It's usually uncompressed, and for most applications, inferior to MP3 and Vorbis. &lt;video&gt; needs similar treatment. That niche is, at this time, best filled by WebM/VP8\. If Apple and Microsoft were to add support for the WebM format, it would only improve the environment for open innovation. H.264 can be considered the "bleeding-edge" codec, heck, they could even add HEVC/H.265 to set off an environment of useful competition (or not). But a "baseline codec" should be established first. Something that publishers can encode their videos in, so that any modern browser can view.

Right now, the discussion has been polarized between free software advocates who often seek to eradicate proprietary or patent-encumbered ideas from the face of reality and those who hold a disregard for the open source values. This way of thinking, and of treating innovation is profoundly dangerous for both the free software community and the patent-creators. The free software community can not afford to be constantly twenty years behind the times in terms of innovation (especially if you subscribe to the law of accelerating returns), and the patent-creators can’t afford for the free software community to involved in actively foiling their innovations. It’s truly great what MPEG has done, and it’s terrible that such a controversy exists around its adoption. The best scenario would be for MPEG or the ISO standards bodies to eliminate royalties. The fact multiple industries can agree upon a single, high quality, interoperable codec should be enough of a market and innovation advantage to waive the relatively nominal money from licensing.

Will this actually happen? I doubt it. Apple seems firmly invested in the success of H.264\. Microsoft may be more willing to add VP8 support if and when the format gains popularity (and especially if Google adds patent indemnification just so they can see a lawsuit made). Mozilla will likely never compromise on principle and Opera might add AVC one day. Given the huge backlash, Google's the most likely to revert its opinion and add AVC back into Chrome in a future release. Yay for hopeless idealism! And since I'm espousing hypothetical and impossible ideas anyway, why not vouch for reform of the U.S. patent system as well? If you think of it, the fact it's such a controversy and that people need to use an inferior product in order to innovate, that smacks in the face of the very Article 1, Section 8, Clause 8 of the United States Constitution:
> To promote the Progress of Science and useful Arts, by securing for limited Times to Authors and Inventors the exclusive Right to their respective Writings and Discoveries.
And this ends what may be the longest blog post I've ever written, revised three times. If you've actually read this through, please consider commenting or sending me a tweet at [@antimatter15](http://twitter.com/antimatter15) (or following me, that would be great!). Also, if I'm misinformed, please inform me and I _might_ revise this yet again.
