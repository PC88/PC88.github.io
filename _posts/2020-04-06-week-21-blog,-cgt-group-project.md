---
title: Week 21 Blog, CGT Group Project
excerpt: Week 21
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:40:27 +0100
#lastmod: 2020-04-06 04:40:27 +0100
---

<hr />

**Week 21 Blog Technology group project, Peter Cannon, CGT Group 2**

The week commencing the start of sprint 4.

This week I moved from the previous weeks inspection of sound to some of the core elements which make up the systems we intend to implement.

This started with updates to the transform class and then moving to the implementation of tick functions in the entity system, which serve to hide the underling functionality of the components contained by an entity. There were also some minor updates to the camera class as there has been some strange interactions when the camera in Maya mode moves left and right.

In order to showcase the now functional physics system and advance the project meaningfully I started developing a demo which would show the physical components being wired to an entity and simulating gravity or some other form of collision. I started this off by following some very helpful steps provided in the book "Learning Game Physics with Bullet and OpenGL" which shows how to rig a transform from the physical side of things to the rendering side. I then added the necessary bullet types and initialisation functions for them to set up the objects and the world, this needs to be a clean distinction as the collision shape, collision object, and motion state must be later wrapped within a physics component relative to each physical entity.

There were no issues in the initial set up of this and I will progress to putting it together next week.