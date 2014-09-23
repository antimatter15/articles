---
title: New Idea Insanely Cheap Multitouch
author: admin
date: 2009-03-14 10:31:24
tags: 
  - cheap
  - mirror
  - multitouch
template: article.jade
---

So I've been thinking about a new design for a Multitouch system. I’ve googled it a bit, and it seems original.

Right now, there are a couple popular multitouch designs. The most popular one right now is probably FTIR, or Frustrated Total Internal Reflection. This is the one used by Jeff Han in his TED demonstrations. There are several variations of FTIR, like Diffused Surface Illumination. Then there is Diffused Illumination, which powers the Microsoft Surface, and a variation of DI is Front DI (where the light source is in front) like the simple DIY MTmini system (where the light source is ambient light). The problem with FTIR, DSI, and DI is that they require the camera to be in the back of the screen. This makes it impossible to retrofit a surface.

The Wiimote tricks by Johnny Chung Lee aren't exactly multitouch. They involve wearing special things to interact. They are interesting nonetheless, but not true multitouch. It's virtually a completely different market, though the Wiimote IR camera may be used with the LaserTouch system theoretically instead of the camera (I was planning to try this out originally).

Laser Light Plane, or LLP is usually similarly used as the ones above. A variant of LLP is the Microsoft Research LaserTouch system (apparently used in Touchwall as well). In LLP, a laser hooked up to a line generator creates a "plane" of infrared light only millimeters above the surface. When something interacts with that plane, light is scattered in all directions. Most systems take light from the bottom, but LaserTouch looks at the light from the top. Wherever your finger touches the plane, it appears to have something like a thin halo around it.

LLP is interesting (especially the LaserTouch variant) because it allows for comparatively really cheap multitouch. The Aixiz 780nm 5-10mW laser (the one(s) most commonly used around nuigroup for LLP rigs). cost less than $10 (though normally 4 or so are used together, and buying goggles for protection from the dangerous light may cost close to a hundred, and the visible light filter is also a slight tax, along with disassembling a webcam to remove the IR filter, making it closer to the $100 estimate by microsoft).

Well, I have a relatively simple idea. You just have a very thin mirror angled just right off to the side of the surface (actually, 2 mirrors, for two coordinates). You are probably thinking that this is only going to be like the normal single-touch systems, which suffer from not being able to detect where you actually pushed when there is multiple points. Actually, the mirrors are only used to determine whether you’ve contacted the screen yet. The position is determined by some magical image processing that hasn’t been implemented yet.

So what do you think of this idea? Did I explain it enough? I’m probably gonna elaborate on this later.
