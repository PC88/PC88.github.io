---
title: Week 18 Blog, CGT Group Project
excerpt: Week 18
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:31:02 +0100
#lastmod: 2020-04-06 04:31:02 +0100
---

<hr />

**Week 18 Blog Technology group project, Peter Cannon, CGT Group 2**

The week completing sprint 2.

This week I had some successes and again regrettably my luck did not hold with Bullets physics systems as well as some other issues.

Il start with the transform class, which has been successfully implemented and checked in its own demo iterating from the model loading demo.

The camera class has been implemented and seemingly works exactly to form. Likewise, its own demo was added and tested incrementally, initially there were some issues with the cross products causing some jarring movement to the left and right, but not forward and back. This has since been resolved I simply had the terms reversed. The camera can support a locked first-person mode, and a fly around Maya style mode. Which brings me to the next implementation.

The event class has been added and linked with the state-handling class being its initial form: to be advanced upon. this was extended this week adding the glfw scroll and mouse wheel bindings to allow for the previously mentioned Maya camera mode. This was also added in the usual demo class and tested alongside the camera.

The texture class was added; however, I could not get the textures to map properly to the 3d model. In order to test this out I wrote a sperate demo to test 2D textures which did indeed function properly and is implemented, this does show we can render textures, but does leave the issues of why the 3D textures are not being mapped correctly or loaded correctly.

Lastly the bullet Demo does appear to crash after a prolonged period of being open -- around 2 minutes, Simon found out. It does also register the same error. This time I Looked a bit more into the error message and can in fact quite the errors with a /FORCE macro. I did also change the demo code to reflect a basic sample code given with bullets latest release to rule out the deprecation idea I previously had. This runs but did leave me disconcerted. I later found out at the project meeting that this was a very unwise fix, and that something else must be a miss with physics. This unfortunately means that we must role physics over to the next sprint again.

So, all in all we completed, 2/6 tasks this week arguably 3/6 if you include the 2D texturing. This is unfortunate but not too disheartening, except for the physics aspects. This means we will roll over the remaining tasks to the next sprint, and we took the prudent decision not to add any more tasks to the list leaving us with: physics, texturing, events, and ECS.

I hope the following weeks will prove more fruitful.