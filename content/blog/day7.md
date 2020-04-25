---
date: Thu Aug 11 23:51:29 2016
description: ""
tags: [  ]
title: "Day 7"
---
OK viewer compiles though now I have to somehow implement a dozillion of functions just to get it linked.

stubs are our friends!!!

~~~
make 2>&1 | grep undefined | perl -pe " s/.+ undefined reference to \`(.*)\'/\1/g " | sort | uniq | wc -l
~~~

gave only 160 results :-) hehe :-)

mostly sound & graphics, some strings stuff (but that should be easy)

anyway I always wanted to implement a renderer here is my STAR TIME has come!!!1111

