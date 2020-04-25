---
date: Sat Nov 12 02:04:48 2016
description: ""
tags: [  ]
title: "Day 43 + image of the day"
---
more long to int and clang warning fixes

there are some jems here like (see below)

chaged texture creation code (hopefully it is also faster now)

`DecodeJPG` - is not implemented? do we need this? Can't we just use TGA???

~~~
int a[5];
//...
if(a)
     do stuff
~~~

or
~~~
UNSIGNED long currentPacket  = numPackets;
while (--currentPacket >= 0)
{
    //do stuff
}
~~~

no parenthesis, what should I think there? is it intended or should I put () around || and change it?
~~~
if (rightFootDone0 &&
        (currentFrame < (mechType->gestures[currentGestureId].rightFootDownFrame0-FOOTPRINT_SLOP)) ||
        (currentFrame > (mechType->gestures[currentGestureId].rightFootDownFrame0+FOOTPRINT_SLOP)))
~~~

~~~
#ifndef UNICODE
int ECharString::Find( unsigned short Char, int Start_Index ) const
{
    // do you see what happens here?
    unsigned short Tmp[2];
    *Tmp = Char;
    Tmp[2] = 0; // <---

    return Find( (ECSChar*)Tmp, Start_Index );
}
#endif
~~~


~~~
p = buffer + strlen(buffer) - 1;
//while (p >= buffer && *p==' ' || *p=='\t') // how did this work???
while (p >= buffer && (*p==' ' || *p=='\t')) // it should be like this
    *p-- = '\0';
p = buffer;
~~~



five (5) layers of if?
~~~
			if (!mover->getTeam() || capturingTeam->isEnemy(mover->getTeam()))
				if (!mover->isMarine() && (mover->numWeapons > 0))
					if ((distanceFrom(mover->getPosition()) < blockCaptureRange) && !mover->isDisabled() && mover->getAwake())
						if (capturingMover->getTeam()->isContact(capturingMover, mover, CONTACT_CRITERIA_VISUAL_OR_SENSOR + CONTACT_CRITERIA_ENEMY + CONTACT_CRITERIA_NOT_DISABLED))
							if (blockerList)
								blockerList[numBlockers++] = mover;
							else
								return(1);
~~~

~~~
// really ???
name[MAXLEN_MOVER_NAME] = '\0';
// maybe
name[MAXLEN_MOVER_NAME-1] = '\0';
~~~

~~~
// at the end of 615 lines long function:
numJumpJets = numJumpJets;
~~~

another out of bounds problem
~~~
	for (int i = 0; i < NUM_SKILLS; i++) {
		for (int j = 0; j < NUM_COMBAT_STATS; j++) {
			numSkillUses[i][j] = 0;
			numSkillSuccesses[i][j] = 0;
		}
		skillRank[i] = 0.0;
		skillPoints[i] = 0.0;
        // this will write beyond the array
		//originalSkills[NUM_SKILLS] = 0;
		//startingSkills[NUM_SKILLS] = 0;
        // should be like this
		originalSkills[i] = 0;
		startingSkills[i] = 0;
	}
~~~

~~~
    // path is an array of 2 elements => comparison always true
	//Assert(moveOrders.path != NULL, 0, " bad warrior path ");
    // right way:
	Assert(moveOrders.path[0] != NULL, 0, " bad warrior path ");
~~~

not fully initializing data structures
~~~
    SkillInfo* skillInfos;
    ...
    skillInfos = new SkillInfos[7];
    ...
    // ???
	memset( skillInfos, 0, sizeof( skillInfos ) );
    // at least hould be
	memset( skillInfos, 0, sizeof( skillInfos )*7);
~~~

I like this one:
```
// this is bad.  However, for release, just let it go on the really
// remote chance it happens.
if ((memBlock < getHeapPtr()) || (memBlock >= (getHeapPtr() + totalSize)))
{
#ifdef _DEBUG
    PAUSE(("Tried to delete a bad pointer."));
#endif
    return (NO_ERR);
}
```

Image of the day: [{{< figure src="/images/devblog/day43_2016-11-12-000015_636x165_scrot.png" alt="click to expand">}}](/images/devblog/day43_2016-11-12-000015_636x165_scrot.png)
