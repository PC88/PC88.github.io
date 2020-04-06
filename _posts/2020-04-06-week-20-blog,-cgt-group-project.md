---
title: Week 20 Blog, CGT Group Project
excerpt: Week 20
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:34:18 +0100
#lastmod: 2020-04-06 04:34:18 +0100
---

<hr />

**Week 20 Blog Technology group project, Peter Cannon, CGT Group 2**

The week ending the 3^rd^ sprint

This week I moved the branch from master and the physics issues are fully closed.

I then moved on to looking at what options we had for sound integration. We have no integration of sound as of yet, and OpenAL -- which was our original choice is now simply not possible as of last weeks switch to a purely static build configuration: as OpenAL doesn't support static configurations. It was also quite dated.

It seems that a reasonable choice after this is WWise. This is an industry grade sound engine which has some of the single best sets of documentation I have seen when inspecting a piece of software. I integrated the .h files and built and remaining aspects of the SDK for our project -- but I have not yet linked them to the project. This is because WWise is very, very large in scale and as a result we would in a similar way to bullet have to integrate aspects incrementally. One object which is as much a useful tool as it is an obstacle in time is that a practical example of the sound system I discovered is provided with the sound package. This is essentially a fully functioning Doom clone FPS called simply "The Cube". The problem with such an example is of course that the size of the source code is rather large and untangling the bespoke sound aspects we may need could be a considerable issue.

We decided that sound is somewhat unessential, however Simon and Axel will look at it after they have dealt with some of the more critical aspects of the project that need attending to: the scene graph and Event system. Which leaves me the tasks of providing a later integration of those systems as well as the building up of the ECS which they facilitate, this will be my tasks moving in to the following weeks and sprints.

Ending Sprint 3 we have integrated physics, and still need to pick up on the remaining ECS and other integral elements in future sprints. This sprint has however removed the largest obstacle from the project so far and I remain optimistic about our chances of delivering an effective submission as a result.