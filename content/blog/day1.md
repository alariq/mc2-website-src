---
date: Thu Aug  4 23:56:58 2016
description: ""
tags: [  ]
title: "Day 1"
---
ok, lets see if it compiles on Windows
hmm..pretty well I can even play it

ok look how things are functioning inside... etc... software renderer, directx8.. but no implementation available

also no sound / networking / keyboard handling / etc... code all core subsystems (including main loop) are binary linked and only header available

big structure taking function pointer and calls them every frame, polls data from devices, does rendering etc...


