---
title: A New Approach to Video Lectures
author: admin
date: 2012-11-21 4:01:39
categories:
  - Vectorized
tags: 
  - concept
  - interface
  - khan academy
  - opencv
  - processing
  - scratchpad
  - simplecv
  - vector
  - vectorized
  - video
  - vision
template: article.jade
---

At time of writing, a video is being processed by my `v2.py` script, it's only eight lines of code thanks to the beautifully terse nature of python and SimpleCV. And since it's clearly not operating at the breakneck speed of one frame per second, I don't have time to write this README, meaning that I'm writing this README. But since I haven't actually put a description of this project out in writing before, I think it's important to start off with an introduction.

It's been over a year since I first wrote code for this project. It really dates back to late April 2011\. Certainly it wouldn't have been possible to write the processor in eight painless lines of python back then, when SimpleCV was considerably in more of an infancy. I'm pretty sure that puts the pre-production stage of this project in about the range of a usual Hollywood movie production. However, that's really quite unusual for me because I don't tend to wait to get started on projects often. Or at least, I usually publish something in a somewhat workable state before abandoning it for a year.

However, the fact is that this project has been dormant for more than an entire year. Not necessarily because I lost interest in it, but because it always seemed like a problem harder than I had been comfortable tackling at any given moment. There's a sort of paradox that afflicts me, and probably other students (documented by that awesome Calvin and Hobbes comic) where at some point, you find a problem hard enough that it gets perpetually delayed until, of course, the deadline comes up and you end up rushing to finish it in some manner that only poses a vague semblance to the intent.

The basic premise is somewhat simple: videos aren't usually the answer. That's not to say video isn't awesome, because it certainly is. YouTube, Vimeo and others provide an absolutely brilliant service, but those platforms are used for things that they aren't particularly well suited for. Video hosting services have to be so absurdly general because there is this need to encompass every single use case in a content-neutral manner.

One particular example is with music, which often gets thrown on YouTube in the absence of somewhere else to stick it. A video hosting site is pretty inadequate, in part because it tries to optimize the wrong kinds of interactions. Having a big player window is useless, having an auto-hiding progress slider and having mediocre playback, playlist and looping interfaces are signs that a certain interface is being used for the wrong kind of content. Contrast this to a service like SoundCloud which is entirely devoted to the interacting with music.

The purpose of this project is somewhat similar. It's to experiment with creating an interface for video lectures that goes above, in terms of interactivity and in terms of usability (perhaps even accessibility), what a simple video can do.

So yeah, that's the concept that I came up with a year ago. I'm pretty sure it sounds like a pretty nice premise, but really at this point the old adage of "execution is everything" starts to come into play. How exactly is this going to be better than video?

One thing that's constantly annoyed me about anything video-related is the little progress slider tracker thing. Even for a short video, I always end up on the wrong spot. YouTube has the little coverflow-esque window which gives little snapshots to help, and Apple has their drag down to do precision adjustment, but in the end the experience is far from optimal. This is especially unsuitable because moreso in lectures than perhaps in any other type of content, you really want to be able to step back and go over some little thing again. Having to risk cognitive derailment just to go over something you don't quite get can't possibly be good (actually, for long videos in general, it would be a good idea to snap the slider to the nearest camera/scene change which wouldn't be hard to find with basic computer vision, since that's in general, where I want to go). But for this specific application, the canvas itself makes perhaps the greatest navigatory tool of all. The format is just a perpetually amended canvas with redactions rare, and the most sensible way to navigate is by literally clicking on the region that needs explanation.

But having a linear representation of time is useful for pacing, and to keep track of things when there isn't always a clear relationship between the position of the pen and time. A more useful system would have to be something more than just a solid gradient bar crawling across the bottom edge of the screen, because it would also convey where in the content the current step belongs. This is something analogous to the way YouTube shows a strip of snapshots when thumbing through the slider bar, but in a video-lecture setting we have the ability to automatically and intelligently build populate the strip with with specific and useful information.

From this foundation we can imagine looking at the entire lecture in it's final end state, except with the handwriting grayed out. The user can simply circle or brush over the regions which might seem less trivial, and the interface could automatically stitch together a customized lecture at just the right pacing, playing back the work correlated with audio annotations. On top of that, the user can interact with the lecture by contributing his or her own annotations or commentary, so that learning isn't confined to the course syllabus.

Now, this project, or at least its goals evolved from an idea to vectorize Khan Academy. None of these truly requires a vector input source, in fact many of the ideas would be more useful implemented with raster processing and filters, by virtue of having some possibility of broader application. I think it may actually be easier to do it with the raster method, but I think, if this is possible at all, it'd be cooler to do it using a vector medium. Even if having a vector source was a prerequisite, it'd probably be easier to patch up a little scratchpad-esque app to record mouse coordinates and to re-create lectures rather than fiddling with SimpleCV in order to form some semblance of a faithful reproduction of the source.

I've had quite a bit to do in the past few months, and that's been reflected in the kind of work I'm doing. I guess there's a sort of prioritization of projects which is going on now, and this is one of those which has perennially sat on the top of the list, unperturbed. I've been busy, and that's led to this wretched mentality to avoid anything that would take large amounts of time, and I've been squandering my time on small and largely trivial problems (pun not intended).

At this point, the processing is almost done, I'd say about 90%, so I don't have much time to say anything else. I really want this to work out, but of course, it might not. Whatever happens, It's going to be something.
