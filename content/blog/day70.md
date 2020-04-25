---
date: Thu Feb 16 01:10:04 2017
description: ""
tags: [  ]
title: "Day 70"
---
fixed BMP loading (new `SDL_ttf` created different bmps, where pixel data was not directly following header end, so have to look at special header field to find pixel data start)

some changes to font rendering

looks like fonts rendered correctly now

some mouse related fixes including wheel (zoom in/out)

