---
date: Sun Feb 26 23:27:28 2017
description: ""
tags: [  ]
title: "Day 75"
---
checked game code with clang analyzer. also code compiles with clang-5.0

unfortunately, analyzer is not that good as I thought... or maybe I ned to add more options?

still did not test fullscreen more even though it is checked in along with all other window changes

clang found bug where pointer was used to compare with numbers though it should be dereferenced

game still can occasionally crash in release mode (maybe in debug as well, but I am playing in release), though I cannot look for a bug which cannot be reproduced.


