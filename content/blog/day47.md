---
date: Sat Nov 19 01:02:15 2016
description: ""
tags: [  ]
title: "Day 47"
---
added conversion between `rgba -> bgra -> rgba` when locking and unlocking, because CPU code expects textures in BGRA, so I have correct colors now

also fixed very interesting issue.

fors code was like this:
~~~
unsigned long s_textureHandle[] = {-1, -1, -1, -1};
~~~

clang was complaining that there is conversion or something like this, so I changed this to:
~~~
unsigned long s_textureHandle[] = {-1u, -1u, -1u, -1u};
~~~

and then today I've got a crash because of this conditional:
~~~
if(s_textureHandle[i] == -1) {
}
~~~

It was giving `false`, what happened in this case is:
1) `-1u` got converted into `0xffffffff`, and promoted to `long`.
2) inside condition expression: -1 got promoted to `unsigned long` with sign extension, so first: it became -1 long, and then converted to unsigned 0xffffffffffffffff, and suddenly it all broke

before it worked, of course. because in construction of `s_textureHandle[]` -1 got converted to `0xffffffffffffffff` as well.

phew, I have to be more carefull with those `longs`

