---
title: Week 27 Blog, CGT Group Project
excerpt: Week 27
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-16 21:02:35 +0100
#lastmod: 2020-04-16 21:02:35 +0100
---

<hr />

**Week 27 Blog Technology group project, Peter Cannon, CGT Group 2**

The last week, week 7 the final sprint.

This week started with a meeting on how to go about delegation of the tasks and if we should take an extension. We agreed that we would not opt for said extension, as the compounding deadlines would be too much to take on. This decision I think is the correct one. With that decision made we went about solving and delegating the remaining tasks. It was set out in our final sprint that the remaining tasks were as follows: critical camera bug, Scene Graph integration, Sound Component Creation/Integration, Bullet Debug Draw integration, Toon Shader addition, Texturing and lastly Ray-Casting/Collision events if possible. Simon and Axel took the remaining sound tasks, and scene graph issues, as well as the camera bug. I took Texturing, responsibility for merging the branches and resolving conflicts and the FBO integration, with the aim of moving this up to a toon shader if possible, within the time. If we had the time I would lastly try and implement Ray Casting.

This final suit of tasks was a tall order, I started by looking to get the Bullet Debug Draw info shown on screen and generally addressing the visualisation of the physical components. I discovered a bug in the physics component constructor which was, not linking the transform data until the tick. This resulted in physical simulation being broken or inconsistent. With this bug fixed I moved to trying to integrate it into the larger project from its own demo.

Once this was added to the larger demo, the physical simulation held up in the ECS, but the debug draw information seemingly did not, now draw calls were made to OpenGL and the graphics behaved as if they were under the effects of the simulation. Yet, the AABB`s were not visible in the larger demo I added several calls in to the bullet API to extract the positions of each of the physical entities, and their positions did in fact line up with where the graphical positions were in relation to the camera. I simply operated by eyeball after this and moved onto another task, I planned to return to this if time would permit.

 Next on the list for the week was the good news that Simon and Axel and collectively managed to fix the camera and this would now need to be merged into the larger system. This was added, on merge pull request 33. Simon had also completed the fleshing out of the sound component, and this would also require merging to the master in preparation for a larger scale presentation demo. However, this was several commits behind the master at the time and had the larger dependencies of the WWise libraries -- of which there are **many**. In order to make the project to continue to run smoothly we halted progress until all branches were brought up to the level of the master after this merge. The conflicts were resolved in a test-branch -- pulled from master -- then moved to the master at the end. This was resolved after merge request 35. It is worth noting that the conflicts here were worth taking time to resolve, as project file conflicts were bound to, and were, in the merge. This was due to the project no longer being able to support MSVC compilers before 2015 versions -- this was a bug which arose with the ECS this week which was fixed with the addition of a pre-processor addition to the project. "_ENABLED_EXTENDED_ALIGNED_STORAGE" to be specific -- this was due to how the transforms were passed in the underling components. We also cut support to 32-bit systems with this merge simply favouring x64 for WWise.

With this completed Simon and Axel, went on to create a demo which integrated a scene graph to manage the ECS, as well as add the sound systems to that demo. While I went to add texturing, a skybox and the FBO integration. I added textures first, then Axel and Simon had completed this extension of their earlier work, I then merged that demo, and began to add the visual additions I had remaining to work towards a presentation demo. A sky box was added, although all of the files for it were read upside down and with a mixed rotation due to the

"renderman" interface which OpenGL uses, this meant I had to take out and manually rotate and adjust each of the images to suit the in-engine visuals.  Once this was added I put in place the FBO which we had integrated in a much earlier demo, this was then switched between and edge distortion filter, and a kernel sharpening filter for which was a quite nice visual effect when applied to the now textured models. I did add a toon shader I had earlier looked out and modified from the book, graphics shaders theory and practise second edition. However, at this point time was near enough up and we simply opted for one of the existing FBO shaders in case of any integration issues.

Lastly, we went about making the presentation where we all worked on a presentation on google docs and talked about which sections to discuss. It was evident that we could not get the project that much over a technical demo, but a feature rich one at that. So, we cut our losses and did what we could with the remaining time. I feel this was executed well and the team really did become much more functional as the project progressed and the experience was very productive -- even if extremely stressful.

This last section I will use simply to detail some thoughts on our presentation itself, and the group:

The presentation I feel went very well on the day. And the idea to have a recorded discussion section at the end I think was a great idea in retrospect, as the hand in mainly had me speaking -- as Axel and Simon had suggested to make the delivery fluid -- however I wanted to make sure all of our voices contributed to the final delivery. -- I would also like to note that we recorded this on OBS with all of us talking on discord of the presentation which, due to me recording on 2 monitors simply had the audio track. This then led to the very, very unwelcome scenario of me having to use music editing software to edit the slides over the audio at midnight the night before. With that aside. The delivery was one I was happy with and despite some of the project's downsides I honestly happy with what was achieved.

NOTE: I have left out some of the details of bug fixes in this last week -- as to do so would make this a veritable essay and I'm aware I am verbose as is: Hence I have left their recollections to the messages labelled to them in the commits on the repository.
