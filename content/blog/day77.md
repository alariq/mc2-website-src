---
date: Sun Mar  5 00:47:47 2017
description: ""
tags: [  ]
title: "Day 77"
---
played with valgrind, fixed some memory leaks.

also, finally, added refereces to fonts, so that we do not load new font every time it is needed, but use loaded if present

found bug in `ABL` scripting - related to 64 bit, well yes not a bug just some work has to be done to fully support 64 bit, do not even understand how I passed 11 missions with broken `ABL`!

