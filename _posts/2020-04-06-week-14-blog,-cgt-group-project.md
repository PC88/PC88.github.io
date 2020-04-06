---
title: Week 14 Blog, CGT Group Project
excerpt: Week 14
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:03:51 +0100
#lastmod: 2020-04-06 04:03:51 +0100
---

<hr />

**Week 14 Blog Technology group project, Peter Cannon, CGT Group 2**

- The first week back

Note: in this blog I will cover not just the progress of the week back, and pick up the naming convention from then on, but will also cover some work done over the holidays.

During the holidays I did some cleaning up of the repository. This started with cleaning up naming conventions to be more uniform and consistent, typically using Hungarian Notation for denotation of members and such, in combination with Pascal-Case for function denotation. We also had a few warnings which were coming from the circular inclusions of header files in the project, so a reduction in the headers was performed across all files. This did lead to significant increases in build times as a result. I would have liked to place everything in a precompiled header file which would have been shared across many if not all files in our project but seen as we still do not quite have the scope of everything which may needed to be included across the project I would not deem it pertinent at this time.

The project did also have to be restructured to make dependencies clearer and to support the multiple configurations of the project which are to come.

I spent a good deal of my time during the holidays looking into DirectX, now this is an extra feature in our project and is most definitely not essential. With that said I would very much like to get it in there and given the learning curve and overhead involved with integrating this in to the systems architecture it was a worthwhile endeavour to place time into from my perspective.

As to our week one tasks, we have set one of our major short comings of last year's goals as our first set of objectives which is the integration of physics into the project using Bullet3. We plan on sticking to our previously set out documentation in having Git be a primary focus for the project, and to progress the project in sprints - as laid out in the project plan. Our first sprint will include the primary goal of trying to integrate physics, as well as add the various updated configurations of the project to match its integration: x64, x86 debug and release and lastly comprehensive model loading -- .fbx and other file formats. This will then be set out in our GitHub project: the resulting sprint being made into a milestone and tagged with the relevant tasks, which in turn, are labelled with the MoSCoW analysis labels allowing us to have a central tracker for the project in the same location we keep the code. This is both concise and allows us to be adequately held to account as well as track our ongoing progress.

This will also reflect our adhesion to a minimum viable solution first, and hopefully illustrate that our time is spent efficiently.