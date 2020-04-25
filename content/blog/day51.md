---
date: Tue Nov 29 00:40:51 2016
description: ""
tags: [  ]
title: "Day 51"
---
was changing `long` to `int32_t` in `ABL` related files... well `extern`s are evil!
consider:

1.cpp
~~~
int myVar;
~~~

2.cpp
~~~
extern long myVar;
~~~

good luck looking for a bug...

ABL uses lots of them!!!

even if you think you've correclty changed all longs to ints, there is such code as:
~~~
long my_stack_var;
memcpy(myVar, my_stack_var, sizeof(long)); // well this you may catch by searching for "long"
// but consider this
memcpy(myVar, my_stack_var, sizeof(my_stack_var));// :O
~~~

I hope I did not leave such cases....

Also was changing(long -> int) in all structures that are saved in order to surpport saves from 32bit systems

Finally, fixed nasty bug when repair truck sometimes was not appearing. As I see, it is uninitialized variable `isOnGui` which prevented it from being drawn

when it happened that it was false, repair truck tried to be drawn as alpha transparent oject, but in fact was not drawn because there was no branch that was drawing objects with just `MC2_DRAWALPHA` flag set.
(see comments in commit for more explanation)

Look like Windows version always initializes memory with `0xff` an so they did not have such a problem. Should I do the same? :-) just to repeat all their issues :-)

no I'll expose all of them and fix them... maybe :-)

Ok, will have a cup of tea and go to sleep, after all I have a birthday tomorrow!
(that is because I am writing it on 28 though this blog records is for day earlier)


