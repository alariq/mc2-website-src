---
date: Sat Nov 26 00:17:16 2016
description: ""
tags: [  ]
title: "Day 50"
---
finished initial draft sound implementation, there are some `wav` files which cannot be loaded neither by `SDL` nor by `SDL_mixer`,
also noise sounds that repacked have to be extracted.

made couple of small fixes like avoiding triggering assert() when dividing by a very small number, happened because currently frame time is faked by me as 16msec :-), and others

even finished E3 mission :-) from .. maybe 10th try, because of anoying asserts and PAUSE()/STOP() triggerings.
some strange issue still remains with trying to render text which is NULL


