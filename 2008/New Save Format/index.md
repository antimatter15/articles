---
title: New Save Format
author: admin
date: 2008-04-26 7:16:54
tags: 

template: article.jade
---

It current save format is subtly known as AXML (though the file extension is still .xml) for Animation XML. This was fine from the beginning (still SVG), then it got some JSON Metadata... but the data was still AXML so that was fine. but the new version has absolutely no XML- all JSON. So what can it be called in this one? I donno.

**Read More To See a sample of the draft**

But i've drafted a spec for the new format. Read more for a sample. It is loosely based JSONRDF (JSON Rich Draw abstract Format), the AXML v2 Metadata, and some other misc stuff. It is much much more extensible and I think it is easier to read (no weird string escaping). It is very verbose, and I dont think compression will really be a goal for this version.

There may be some changes to the draft. One i can think of (but am too lazy to include in the draft) is to rather than use an array to store frame, use an object associated with the frame id.

so rather than
[{
index: 1,
changes: {...}
}]

you have:

{
frame1: {
//some frame metadata
changes: {...}
}
}

its considerably easier to read (latter) and likely easier to parse

If you have suggestions for the name of the format, please feel free to comment
