---
date: Tue Nov 29 00:40:03 2016
description: ""
tags: [  ]
title: "Day 52"
---
fixed memory leak in `gosAudio_CreateResource`

in training mission 5 `"terminationResult"` variable was screwed (see mission.cpp 667 - 676 lines)


apparently guys had a strange sense of humor and added playing of win/lose tunes if `terminationResult` was not as one might expect to find out ABL issues, and apparently training mission 5 has them.

I do not know if it had them before, or they we caused by my recent changes in `abl` code (`long->int`), I hope not. Will have to check tough


