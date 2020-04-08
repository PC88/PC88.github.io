---
title: Week 26 Blog, CGT Group Project
excerpt: Week 26
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:51:23 +0100
#lastmod: 2020-04-06 04:51:23 +0100
---

<hr />

**Week 26 Blog Technology group project, Peter Cannon, CGT Group 2**

The week ending sprint 6 -- commencing the final sprint 7.

This week I worked on completing the ECS, implementing a debug draw for Bullet -- to see where the entities are placed, a merge of Axels Scene graph, as well as helping with some of the issues with that, and finally working on an irritating error with the existing camera class which is untimely and problematic.

I will start with Axels Merge:

Axel`s work did have some conflicts in the Entity class, as his branch was some more commits behind the master and required some resolutions. His work largely provides a simple container class which mimics the underlying interface which allows all entities, and components to have similar calls performed on them: these mainly being "Render", "ImGuiRender" and "Update". I did help in some areas of this as well, mainly how the camera would be passed in and how it would be managed as Axel had some questions on this specifically. It is also worth noting that this caused some initial issues as Axel had planned to use templates to allow any type to be passed to the container, although we only have need of one: Entity. When he tried to pass this the version of the branch he was using was outdated and used the older pure virtual version of the entity class, it was later changed to be an optional interface rather than mandatory. This created some initially confusing template errors which were eventually resolved.

I have as of this week completed the ECS system. This is still likely to be modified in future as we rush towards the end of the project. As mentioned in last weeks blog a solution to the camera errors was a singleton camera implementation which did successfully solve the issues and make the demo function. This unfortunately led me to uncover to bugs which had until now escaped my notice.

The first was that the camera appears to function fine, until when moving left of right the rotation is affected slightly -- and only when close for some reason. I have tried changing around many values within the camera class and the solution still evades me. As of now I have a solution which I have gotten from the very helpful learn OpenGL online tutorials which provide a type of camera class which I will integrate to hopefully provide a expedient and effective solution.

The second bug I uncovered was that the transform data passed to the components -- a long previous blog discussed this topic -- has some kind of issue where the model`s model matrix is mangled when used from the components weak_ptr. This was not evident at first as the entity does render but when the camera moves it forms an almost kaleidoscopic warping, but some how retains a central position. I have honestly no idea how the specifics of this manifest, but this bug was solved -- at least for now by providing a freshly initialised model matrix to the graphics component and subsequently modifying it each frame.

Being aware of time constraints and seeing as the camera is still usable, I promptly moved on to a small, but utterly mandatory section of the project -- the graphical component of Bullet Physics. What I mean by this is: the debug draw functionality. We simply need to see the physics entities rendered to see where to place and move objects. I initially tried a modern OpenGL implementation from an online forum which did have its draw called each frame but, irritatingly, did not render anything. This leaves me with two remaining options that I will try in the coming days -- that of another modern OpenGL render in the hopes this implementation will be successful, and finally a easier to implement but CPU side legacy renderer for the debug info. This is a conceit I would rather not make but may have to be given. Seeing as it's purely for debug info and wouldn't be in a release it does seem excusable. A template for this implementation is laid out in the book Learn Game Physics with OpenGL.  

My final task this week was to order up a remaining list of tasks and organise a meeting to discuss our options with Simon and Axel. I created a new final sprint on the Git project, updated the millstones and added the new and remaining tasks to a final milestone. This leaves us with 7 major tasks remaining: The Bullet Debug draw, Ray-Casting/Collison Events, Sound Component, Scene Graph integration, a toon shader, the Camera bug fix, and lastly the addition of potential ImGui docking which can provide a menu system -- but this would be last in priority. This is undoubtedly a vast task, and with 7 days left to us means we would have to realistically manage over one task per day.

This is I think optimistic at best, we will have a meeting tomorrow to go over progress and discuss how we manage this final set of hurdles. Some of these tasks are far easier than others it is worth noting -- I already have a toon shader implementation looked out from a book: Graphics Shaders theory and practise. The scene graph integration is trivial given that the ECS is now finished. Simon has also been working on a demo which to his credit apparently implements special audio using WWise and has done so a separate branch, which may offer a speedy solution to sound component code. Lastly, I can also hope, as well as persevere, with the camera alternate implementation and the debug draw code for bullet.

As a final statement on this week, the stress is becoming very strongly felt. I have at this point committed almost 200 commits to the project and made some 500,000 changes and deletions. This leaves me very, very burnt out and I can feel my productivity slipping as time goes on. I mention this as not only is it a very real problem, but we have the option of an extension available due to the ongoing coronavirus crisis, but the prospect of another 2 weeks of this project layered on top of another university module deadline: algorithms and collections, is a dire prospect. We will discuss this tomorrow, and I will endeavour to continue to work to the best of my ability.