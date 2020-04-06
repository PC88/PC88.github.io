---
title: Week 16 Blog, CGT Group Project
excerpt: Week 16
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:16:48 +0100
#lastmod: 2020-04-06 04:16:48 +0100
---

<hr />

**Week 16 Blog Technology group project, Peter Cannon, CGT Group 2**

This week was the end of sprint one. In which we set out the tasks of: Physics integration, comprehensive model loading, and updated configurations -- support for x86 x64 debug and release with the physics library additions. We arguably hit 2 out of 3 for these tasks as physics still escapes us for reasons that will be the main discussion of this blog and I will conclude with our new set out of tasks.

Physics with Bullet has indeed been problematic. The issue was runtime exceptions which have been very troublesome to diagnose, I had initially thought it was a configuration setting with the project but having inspected the configurations I cannot find anything amiss, much to my chagrin. Axel and Simon are also getting strange errors with the project on their builds, unresolved externals when using bullet -- specifically with the shape classes(btShape). This issue even now remains elusive, despite my best efforts I will continue to try and resolve the issue.

As to where this leaves us at the end of this sprint is simple; we carry over our tasks to the next sprint, and endeavour to catch up.

Now despite some advice I have been solicited our next sprint will be very intense. This is not because I wish to annihilate my mental will early on in the project but simply because should this set of tasks be completed. The project would be well on its way to being completed and move from a comprehensive tech demo to a game shortly thereafter.

 Sprint 2 will consist of: Texturing with OpenGL, The Event system, and ECS(Entity Component System), Camera class, and lastly a transform class. This sounds like a lot, and it is. There is a good chance some of these tasks may also be carried over to following sprints, but in order to motivate progress towards this projects completion early I think it would be a wise idea to set out the tasks Infront of us early. This is also with the addition of Physics from last week.