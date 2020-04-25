---
date: Sat Dec 17 00:57:03 2016
description: ""
tags: [  ]
title: "Day 55"
---
fixed issue with salvage airplane not being drawn.

Apparently, it is same old issue when I changed signature of virtual function in base class and forgot to change it in one of the derived classes....

in this particular case it was getting node position by name in model. I changed it to `const char*` instead of just `char*` in one of the first changes to the code (even before I added code to git)

So, defaut implemetation was just returning `0,0,0` and it was used to get target position, so airplane just could not come on screen because `0,0,0` was somewhere far far away

Also added very simple "frame debugger", when I can scroll back and forth in draw calls and break on one which interests me. It already proved to be quite useful in investigating rendering loop

