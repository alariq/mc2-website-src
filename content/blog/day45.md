---
date: Mon Nov 14 01:50:25 2016
description: ""
tags: [  ]
title: "Day 45 + image of the day"
---
implemented proper (well.. I mean, it works sometimes) texutre lock/unlock

figured out why mouse cursor is not drawn sometimes (mc2 mouse is processed in a separate thread. Something like `this` variable was set or not set depending on some strange reasons)

we shoulld always assume it is not in a separate thread and that is it!

spent whole evening tracking strange issue when mechs would not go where I told them... but would do it if I said to shoot, apparently I had 2 errors in `timeGetTime()`

and overall I was wrong by `1e3` in 2 places :-), thanks gdb and watchpoints, now camera also works better and I even finished a mission, though, it crashed on a mission end screen :-)

so, quite a productive evening today.
thank you all :P
bye!



Image of the day: {{< image-ref src="/images/devblog/day45_2016-11-14-015725_3841x1201_scrot.png" alt="click to expand">}}
