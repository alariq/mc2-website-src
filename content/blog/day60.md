---
date: Sat Dec 31 00:07:24 2016
description: ""
tags: [  ]
title: "Day 60"
---
Wow, found out a bit more detail about how rendering is done in MC2.

In `tgl.cpp` there is usually `Update` and `Render` methods. So `Update` updates and transforms shapes AND at the same time allocates triangles in `masterTextureNodes` accordingly.
And if there should not be any texture then `nodeId == 0xffffffff`.

Later in `Render` method, necessary vertices are added. Somehow, those methods should be in sync, so that we add exactly same amount of triangles that were allocated in `Update` method.

In a same way, `nodeId == 0xffffffff` if no texture should be used, also in this case `masterTextureNodes[0]` is used to store triangles info.

Found all that when trying to figure out why windows sometimes become transparent and sometimes not. So have to make sure that texture handle 0 means no texture and just add fake texture when renderer is initialized, so that no valid texture wil have handle 0. Also have to figure out, what does it mean when terrain is drawn with texture handle 0, should those triangles be drawn or can we just skip them (apparently skipping them seems to be ok, but have to make a thorough check).

And finally - even if I've found a problem with windows, it is still a question why they are drawn only in some cases and in other cases, they are not drawn.

