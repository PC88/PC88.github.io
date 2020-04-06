---
title: Week 17 Blog, CGT Group Project
excerpt: Week 17
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:20:05 +0100
#lastmod: 2020-04-06 04:20:05 +0100
---

<hr />

**Week 17 Blog Technology group project, Peter Cannon, CGT Group 2**

The first week of sprint 2.

I believe I have found the issue with the physics system for our project. I found that when using a different definition for the collision configuration the project compiles and runs for now. I think this is most likely due to the fact that the code I was creating pieces of the demo from being from a book, Learn Game Physics Bullet Physics and OpenGL, which used code samples -- which I must assume -- utilised out dated/deprecated instantiations for the abstract classes. This would lead to object splicing and could cause such a memory corruption error. This does seem unorthodox, as the book is not too old -- 2013, and doesn't seem to make use of any -- at least declared deprecated functions.  However, given that the code compiles this answer will suffice for now.

The base classes for the event system, transform and camera class have been added and the transform class has been almost entirely completed. The class as of now is not optimised -- all matrix functions are not performed inline as they typically should be, and the code is extensively commented. This is critically because I wish for maximum readability in this part of the code, most transform classes where matrix operations are very hard to understand at a glance as they tend toward performance. This can be changed for us later down the line but for now I have played out even specific functions to mirror their mathematical counterparts.

I aim to flesh out the remaining classes in the coming week.