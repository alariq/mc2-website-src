---
date: Sun Mar 12 01:00:09 2017
description: ""
tags: [  ]
title: "Day 83 + image of the day"
---
!!!!!yay found and fixed bug.. no 2 bugs at once! one was causing other in a very weird way.

When we have mech with blown hand(s) in engine it is implemented as mech without handes + mech with only left hand (no body) and right hand (also no body)

The thing is that once we do not have body `updateGeomery` was not called and texture handle for hand(s) was not updated, but in render function it was updated. So, during `update()`, `addTriangle` was called with one `nodeId`, but in `render()` it tried to add vertices to another `nodeId`, and of course could not find it, leading to "Flags do not match either set of vertex Data" message.

I noticed this during early stages of porting, but thought it is something innocent, though, I did not relate it with issue when some polygons magically disappeared in live mechs of the same type (polys were popping in and out depending on view angle which was even more strange). Apparently one issue was causing another, due to broken vertex lists.

But now it is fixed, and I can sleep well!

but first drink some tea!

Image of the day: [{{< figure src="/images/devblog/day83_2017-03-12-010816_3841x1201_scrot.png" alt="click to expand">}}](/images/devblog/day83_2017-03-12-010816_3841x1201_scrot.png)
