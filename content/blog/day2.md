---
date: Sun Aug  5 23:12:19 2016
description: ""
tags: [  ]
title: "Day 2"
---
ok, leys start porting! yay!
hm... how do I even compile it...
lets go into directory with smalles number of files
`CMakeLists.txt` based on `.vcproj` files
~~~
cat Stuff.vcproj | grep ".cpp" | perl -pe 's/.+\"(\w+\.cpp)\".+/\1/g' >> CMakeLists.txt
~~~
ok, compile... oh my..

and of course nobody cared for include filename CaSEneSs,

so small script to bring all files to lowercase

small script to bring all include to lowercase and fix slashes

ok better but still...

lots of asm code, in some places there is equivalent C++ code, but looks like it was never tested, some stupid mistakes there, like variables are even not declared, or function calls used which do not exist

probably only ASM branch was used since some moment of time..., ok still switch to C++ `#ifdef` path and just fix it


