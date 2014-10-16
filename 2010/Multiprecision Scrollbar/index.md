---
title: Multiprecision Scrollbar
author: admin
date: 2010-11-10 8:48:32
categories:
  - Uncategorized
tags: 

template: article.jade
---

Scrollbars are great for most applications, but start to lose usability when scrolling large documents (or collections of such documents). Infinite scrolling produces a nasty user experience with normal scrollbars.

This is an experiment which combines certain aspects of different navigation systems.

The modern scrollbar basically has a proportionally sized block which represents the user's viewport. The user drags and drops the metaphorical viewport into a location and the actual viewport scrolls to that area.

This experiment is based on a vertical rendition of the SIMILE Timeline Widget, where at the center, is a fixed viewport, and the content around it is dragged to manipulate the viewport. This is advantageous in several ways, for large documents, the modern proprotionally-sized scroll bar becomes very small and harder to grab (fitt's law). While a non proportionally sized scrollbar may fix this, it would eliminate the useful knowledge of the size of the viewport.

With infinite scrolling systems commonly employed in sites and applications where a data stream is useful, the scrollbar doesn't function ideally since dragging it to the bottom doesn't get you to the actual end and when the next page is automatically loaded, the bar behaves erratically. By not associating the abstract top or bottom of an arbitrary subset of the page, the scrolling is uniform and universal, pagination happens naturally.

Coarse, Medium and Fine scrolling is accomplished by utilizing the different scrollbars intended for scrolling the page. The extended scrollbars appear once the scrolling is initiated. The precision of scrolling is proportional to the horizontal position of the mouse. This is inspired partly by the scrubbing bar on the iOS iPod application.

I wont pretend this is a solution that's perfect for everything. People are accustomed to scroll bars which operate on a somewhat strange notion that the content goes up when you drag down because you're moving the viewport rather than the content that lies below. Since this approach opts for dragging the content, the motion is reversed and may require some time to become accustomed to.

Mouse movement is somewhat awkward as to navigate to an arbitrary section, one must go to the right edge, mouse down, drag to the left move down and move back to the right edge before letting go and doing stuff.

It's designed for scrolling large multisectional documents or collections of such documents, with titles in chronological order. It's not so great for scrolling unstructured viewports.

[https://github.com/antimatter15/multiprecision-scrollbar](https://github.com/antimatter15/multiprecision-scrollbar)
