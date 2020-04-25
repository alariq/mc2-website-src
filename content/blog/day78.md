---
date: Mon Mar  6 00:51:35 2017
description: ""
tags: [  ]
title: "Day 78"
---
Looks like I finally found what was causing `areaTriggerAdd` crash, - `ABL` did not realy work with 64bit.

Now it does, I hope :-)

Though, found whole bunch of 32<->64 bit problems in `warrior.h`, some mechs would not go far, esp. repair truck, then, some stats were weird in info (i) screen. Found out that some data types were `int[]` but memcpy was done with `sizef(long)` :-/ I thought, I was attentive when changed those arrays to `int`. 

So have to 1st) ensure no data overwrite occures 2nd) actually change all save/load data to not contain 64bit values in order to be compatible with 32bit saves.

