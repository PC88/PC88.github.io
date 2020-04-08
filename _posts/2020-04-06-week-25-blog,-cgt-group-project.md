---
title: Week 25 Blog, CGT Group Project
excerpt: Week 25
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:49:17 +0100
#lastmod: 2020-04-06 04:49:17 +0100
---

<hr />

**Week 25 Blog Technology group project, Peter Cannon, CGT Group 2**

The week starting Sprint 6,

This sprints task is to make as much progress as possible towards the end of the project as we near the submission time. The main stay of my focus this week has been directed towards the ECS and event system integration. This involved the merging or Simons work in this area, that being; Simon has created a functional event system and accompanying demo. Which will now be merged to master and integrated; Axel has created the scene graph container and interface for the entities which will have to be integrated soon, but is not ready yet, and adjusted to fit my implementation of the Entity interface and any changes to come in the following week on either components or the entities themselves.

The merge of Simons work was simple with no conflicts, his demo shows a message being send to a class and output to the console but can accommodate any type of message being sent. This system mirrors an event system implemented in an early version of the "Cherno" Engine which the project takes some inspiration from.

Outside of this I largely continued work the Entity Component system, passing values to the wrapped graphics and physics components has proven a little more challenging than anticipated. Mainly due to the access for camera attributed to every entity, as every entity must use the same View and Projection matrices -- thus they must be correctly disseminated through the system in question. This challenge is further exacerbated by the fact that I wish to use the current demo I am working on, the Entity Components Demo, to illustrate to Simon and Axel how the system works incrementally. I have done this by creating 3 entities, one being utilised with all the raw code, the next being partially wrapped with explicit calls to the components, and the final one being entirely wrapped in the abstraction. This way they can see how we go from many lines of code to essentially three lines. Those lines being constructor, update, and render. This does mean however that I need a camera to accommodate these changes. I have tried to utilise the current camera but this was largely designed with the idea that I would be cycling through a number of entity model matrices and multiplying them by the cameras matrix in one area: a scene graph, but without the scene graph to manage the entities -- especially in the case where I want to didactically show the calls to components, which is not their intended use -- I need to have almost global access.

The next solution I will implement for this is a singleton where there will only ever be one camera, and I can in effect call on it from anywhere.

The last piece of work I did this week on the Entity Component system was the slow process of rewiring calls, such as load models, load shaders -- now allowing for the entities to have these paths given to them on construction -- this was a refactor from the demo system which performed it before.

There is still much ground left to cover, and I am all to aware of the time constraints, the stress -- as it always does - is mounting and I will endeavour to manage it as best I can with the remaining tasks.
