---
date: Mon Nov  7 00:43:04 2016
description: ""
tags: [  ]
title: "Day 40 + image of the day"
---
continue to get real game (and not only menu, though I got to other menus :-)) running.

implemented (coarsely and file times are not correct yet) `FindFirstFile` and friends

some fixes in a `Heap` class (mainly `VirtualFree`)

other fixes here and there.


oh, and yesterday I did some function parameter changes from `char*` to `const char*` and as a result got bitten by it, because suddenly if there were derived classes and that function was virtual then it was not an override anymore :-)

so had to go through all such places and fix them.

phew.., hope I fixed all of them

Image of the day: [{{< figure src="/images/devblog/day40_2016-11-07-004357_3841x1201_scrot.png" alt="click to expand">}}](/images/devblog/day40_2016-11-07-004357_3841x1201_scrot.png)
