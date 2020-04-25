---
date: Sat Sep 17 02:00:13 2016
description: ""
tags: [  ]
title: "Day 10"
---
 continue to fill `main()` function and run Viewer

implemented `gos_CreateMemroyHeap` and friends

caveat: `_open()` calls `File::open(const char* bufer, int length)` instead of system open
because

`    #define _open open`

should be

`    #define _open ::open`

or even better 

`    #define _open my_super_open`

and then
~~~
FILE* my_super_open(...)
{
    ...
}
~~~

caveat2: code uses long and assumes that it is 4 bytes :-(


