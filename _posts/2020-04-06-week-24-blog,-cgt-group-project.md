---
title: Week 24 Blog, CGT Group Project
excerpt: Week 24
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:47:38 +0100
#lastmod: 2020-04-06 04:47:38 +0100
---

<hr />

**Week 24 Blog Technology group project, Peter Cannon, CGT Group 2**

The week ending the 5^th^ sprint

This week I was able to start doing a lot of the wrapping which is needed to advance our project to the point where we can steadily add features to the world, which will eventually progress to a game environment.

This involved fleshing out the until now barren, for the most part, entity and component classes. This started with filtering out the component specific code for physics: the motion state, collision object, and collision shape for physics, and the transform to the entity classes. The transform being moved a way which both preserved ownership semantics as well as being usable for both graphics and physics components.

The transform was by far the most arduous task to overcome this week. The transform had to be made from floats, as mentioned in a prior blog, but it also had to be of a fixed size, 16 floats to resemble the memory layout of a 4x4 matrix. I wanted to keep the size static for this reason, to ensure that the size was fixed and could not be made mutable at runtime, like a vector. This as an idea seems simple enough, just have an array propagated to each component owned by the entity and its all fine and dandy... of course, its never that simple. It turns out that arrays, just plain old arrays, don't delete themselves properly when managed by C++ 17, without being supplied the specific deletion method in the constructor, usually requiring the programmer to simply write the call to: "delete[]" as opposed to "delete" on each entity or provide std::default_delete<float[]>(). The latter option is what I ended up implementing.

However, as it also turns out: if you call std::make_shared, as is convention on the instantiation of a shared_ptr to ensure no dangling references MVSC has a specific compiler error which stops this, so manual instantiation is needed -- we again implemented this work around. But the pointer madness does not stop there; the weak_ptr which is propagated to the components -- to keep ownership nice and tied must have whatever its pointing to accessible to the underlying component which owns that weak_ptr. This is not so obvious as it turns out that weak_ptr`s cannot be dereferenced in the standard fashion that shared_ptr`s  can: the need to have the function lock() called on it which then provides a shared_ptr from the original the weak_ptr -- which is now safe to dereference as a weak_ptr may be deleted at any point. This then, has to be passed into a contigious memory form to be manipulated by the graphics component -- using glm::make_mat4, which requires the shared_ptr created from lock to be returned in to this function. And then... finally, can be sent to the GPU side of the equation having accurately passed the physical transform to the graphical component.

The above ordeal was found out the hard way and substantiated the majority of my time this week. This left our project at the point of having a demo which has a good deal of the wrapper classes, and a physically modelled plane with infinite mass representing the ground, as well as 2 distinct entities coloured with differing graphics components and manipulated by two separate forces acting on their transforms -- in combination with gravity.

This brings us very close to being able to finally tie a ribbon on the projects large scale integration and use hopefully the remaining sprints largely for the integration of gameplay functionality rather than a tech demo as it currently stands. This will be a challenge, but one I still think is doable.

Simon has been implemented an event system in branch which is separate from the master and is in a suitable condition to be merged and utilised. Axel has completed the container for managing and manipulating the ECS this week. This when brought together as we will be doing in the next week or so will hopefully stand us in good stead to make rapid progress to something altogether a bit more substantial and unified. -- Simon is also working a solution to our current sound conundrum with WWise and has told me that he is having some success in that regard.