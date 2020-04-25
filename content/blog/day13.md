---
date: Wed Sep 21 00:14:35 2016
description: ""
tags: [  ]
title: "Day 13"
---
continued to debug `long` vs. `int DWORD typedef`

figured out that `mov %var, %esp` is the way to get `this` pointer, because of `thiscall` convention, thank you `gdb`

changed `database.cpp` and some other files to correspond to new `DWORD` size

uncommented stuff in heap 

