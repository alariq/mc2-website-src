---
date: Thu Dec 22 01:12:20 2016
description: ""
tags: [  ]
title: "Day 56"
---
small stuff, fxed some warnings, but also fixed annoying black tiles in terrain, that was weird... for some reason texture is drawn with alpha blend and it has zero alpha, but in fact it should not be drawn with alpha test in first place. Well, there is type passed (`gos_Texture_Solid`) when it is created, but.. well, it has alpha channel and was drawn with blending so, why should I set alpha channel to `0xFF` manualy? Well, I think I have to, though it is still strange why quads without detail are drawn with alpha blending enabled...

Also while on it, I've added handling of `gos_Texture_Detect` type (detecting if texture has something usefull in alpha channel and make it transparent or not)

also added texture filter and address mode handling, which exposed ugly lines between chunks of terrain texture

