---
title: Week 22 Blog, CGT Group Project
excerpt: Week 22
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:42:46 +0100
#lastmod: 2020-04-06 04:42:46 +0100
---

<hr />

**Week 22 Blog Technology group project, Peter Cannon, CGT Group 2**

The week completing sprint 4.

This week was the first big stride towards putting the whole project together. I spent most of my time this week assembling a demo so show graphical and physical simulation working in parallel as an early version of the Entity, and eventually the Entity Component, system.

I did plan on having 3D texture mapping in on this demo as well, I was however not able to get it in, in time sadly. The issue with 3D textures being that the textures can be seen in GPU memory, via Nvidia Nsight but aren't rendered on the model, the model being black. This means that there is most likely an issue with the indexing, or IBO object which is an issue for the future.

The demo does successfully simulate a model being affected by gravity via a linking of the physical simulation with the necessary graphical hooks.

Initially we had thought to house a transform class within the entity class which would then be propagated to the corresponding components which would all be owned via the entity. We still do this, but in a rather round-about way. This is due to a complex issue with the way Bullet deals with its physical transforms and was what I spent the majority of this week contending with.

The issue arose when I had tried to pass the transform to the physical object. A b2Transform class is constructed from a series of floats, a simple array of 16 floats. This mean that our transform would have to consist or be transferable to the same format and then would have to be convertible to values which suit glm, our math library, and bullet. As it turns out this issue has arisen for many developers before, and is subsequently solved with Bullets Transform class`s helper function "getOpenGLMatrix". This function takes a pointer of floats -- an array typically, and returns them in the memory layout of a matrix, from the physical transform: thus, enabling a link. Conceptually however this changes things, as now the Transform - that being the physical transform - really owns the transform of the entity. This then propagated to the remainder of the entity system. How I choose to keep our design intact in by having the floats which make up the transform be housed in the entity class and then propagated down. This I realise might be hard to follow, but what happens is we have a blank array at the top of the hierarchy: the entity, this is then propagated to the physics component and filled out upon construction, via weak_ptr, thus ownership is maintained by the entity. This is then finally sent to the graphics component to be rendered.

The above however is not quite the crux of the issue. The most work, and outright mental trauma, was caused when I tried to get the memory layout in to GLSL. As the Row-Major and Coulomb-Major ordering used by graphics API`s needs to comply with the ordering used on the CPU side this usually means transposing the matrix, however I had to learn the hard way that the memory layout of the floats were layed out the same way in OpenGL and Direct3D, despite being treated differently. This means that they simply have to be passed in a contiguous manner, via memcpy, or similar function -- I tried many and eventually landed on glm::make_mat4 for an easy conversion which then finally yielded the transforming properties we desired.

Much of what was discussed above was gained from insight provided by the book, "Learning Game Physics with OpenGL." Which has been of great help.

I would close with the statement that now we are extremely close to having a complete ECS, as the demo just needs the wrapping layers and the ECS is complete. Physics is also solidly complete in terms of integration and allows us to start implementing puzzles, and gameplay features when the wrapping classes are there. Again we trail behind the goals, but I believe that gap is close to being closed.