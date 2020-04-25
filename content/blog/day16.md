---
date: Sun Sep 25 01:11:20 2016
description: ""
tags: [  ]
title: "Day 16"
---
Continud with long -> int conversions. `Packet.cpp/h` converted.
found nice checksume function there, 
~~~
int PacketFile::checkSumFile (void)
{
    // ...
	int sum = 0;
	MemoryPtr curFileByte = fileMap;
	for (unsigned int i=4;i<fileSize();i++,curFileByte++)
	{
		sum += *curFileByte;
	}
	return sum;
}
~~~

and interesting random tmp file name :-)
~~~
PacketFile tmpFile;
result = tmpFile.create("AF3456AF.788");
if (packet >= numPackets)
{
    numPackets++;
}
~~~

still in `InitializeEngine` function

