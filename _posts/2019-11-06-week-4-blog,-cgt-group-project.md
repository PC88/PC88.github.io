---
title: Week 4 Blog, CGT Group Project
excerpt: 
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2019-11-06 05:55:36 +0000
#lastmod: 2019-11-06 05:55:36 +0000
---

<hr />

## Week 4 Blog: 

This week I spent a good deal of time adding CICD tools to the project as I was initially directed towards Travis CI which after a good deal of looking in to does not appear to natively support windows to any large degree. I came across a great deal of work arounds to integrate it some using bash and others, I did however decide to look for other options as this extra work of using the work arounds does not seem like a wise choice initially for us. This led me to find Azure pipelines which is Microsoft`s alternative which seemed like a much better fit for us as group, windows native initially -- and can be extended to other OS and platforms if we so choose.

I then actually hooked this up to the repository which worked well, except for one issue. This being that the build is integrated with our version control and runs, however it will fail on an issue not at all to do with the code base. It fails on a issue with not being able to find MS Build tools. Now I have checked these build tools and I have them installed to be sure, but it was also complaining that the visual studio 2019 build tools were also absent. I since installed visual studio 2019 and its requisite build tools and their still appears to be an issue here. I will aim to fix this, but it has consumed enough of my time for now and still serves the purpose of telling us issues, except for the MS Build error.

I also continued work on elements of the GDD. This being elements of the look and feel simply clarifying its tie to H.P. Lovecraft and some of the justification behind this.