---
title: Week 15 Blog, CGT Group Project
excerpt: Week 15
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:13:11 +0100
#lastmod: 2020-04-06 04:13:11 +0100
---

<hr />

**Week 15 Blog Technology group project, Peter Cannon, CGT Group 2**

This blog is taking place on the second week of Sprint One**.**

The initial progress made on the project as of this week is the following: I have added support for all configurations both x64 and x86 debug and release. This was a long a tedious task, given the amount of tendencies bullet3 brings -- 3 libraries base: collision, dynamics and linear math. I also opted to include the 3 modern Bullet3 counterparts of those libraries: Bullet3, common, dynamics and linear math.

Once these libraries had been included and added to the newly updated folder structure, I hit the first issue of coming back. The .h files would be fine when included, but as soon as I implemented the most basic of features in the project for bullet, which was the creation of a world object, collision configuration and a solver. The project then threw a runtime error, which proved very hard to reason why this was the case. I suspect this is something wrong with how the bullet library is built as this type or error, in my limited experience, is very hard to diagnose and I have only ever had the previously with wrong config settings. For example, running a x86 project with a x64 dependency or vice versa.

The above issues were also implemented in our demo framework and this should allow us to debug this issue more effectively as time goes on, in isolation it is most definitely bullet, as no other demos throw the issue, and if the physics engine calls are removed the demo will run. This is where most of my time with this week, as this is a priority task for us as we should have had this in for some time now.