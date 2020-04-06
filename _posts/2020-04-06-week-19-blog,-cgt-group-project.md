---
title: Week 19 Blog, CGT Group Project
excerpt: Week 19
author: Peter Cannon
categories:
  - topics
  - Acedemic Project Blog
background-image: flickr-froderik.jpg
#date/lastmod are optional
#date: 2020-04-06 04:32:37 +0100
#lastmod: 2020-04-06 04:32:37 +0100
---

<hr />

**Week 19 Blog Technology group project, Peter Cannon, CGT Group 2**

The week starting sprint 3 of the project

On advice given in this week's meeting I have removed the /FORCE commands and began looking for a solution to the Bullet physics runtime errors. The issue seems to be primarily with the CRT(C-RunTime-Library).

Initially I had never encountered the mis-match issues between the code-generation settings, which can cause the issues our project is suffering from. Those primarily being that of CRT miss-matches for each of the dependencies. This left me with a few options to try and weed out this ever irritating issue:

I can rebuild all dependencies in the project dynamically, which theoretically would solve the issues.

I could build all dependencies statically; this would mean building the entire dependency tool chain again and matching every configuration -- which is more time consuming but would also theoretically solve the issue.

Lastly, we could explore other options for physics, which is a considerable risk as the project is centred around this physics system integration. Another engine may either be too steep a learning curve: as it won't be modelled on Box2D`s physics simulations which allow me to have at least some initial insight as to how Bullet3 works in execution.

First, I tried option one listed above. I read through the docs for Bullet, and seen that it was very unfortunately not "natively" supporting dynamic builds. This was discovered from a post by the creator of Bullet. With that said I felt it would still be prudent to try a dynamic build as, although the claim to not support dynamic CRT, the project C-Make settings do support a shared lib build and critically a dynamic CRT build. I attempted this and integrated the result into our main project and the project still suffered the runtime memory issues.

Failing this attempt, I moved to option two, but seen as option two was grossly time consuming, I built this project first in a separate project, as in a totally different from the ground up Visual Studio solution, with a simple port of the C++ code from the last. Incrementally I added the dependences from a static build of each with the most up-to-date configurations. This proved very fruitful, I learned with taking my time with this aspect that with dependencies like glew, it seemingly did not matter which CRT was used for what build was integrated, as it does not use the CRT like other dependencies. On a similar note ASSIMP also noted in its documentation, somewhat dubiously I think, that it *can* be built with dynamic integration to a static project. This I tested and it always caused issues when built dynamically. Alas at the end the project built with the new tool chain and no issues could be found to the best of my testing.

I still had one more hurdle with this, however. Having now built a successful project which mirrored the current git repo, it had to be ported to that project. Seemingly simple enough a task. I added each of the dependencies incrementally with builds with no anomalies, until of course bullet was added. In which case I again got memory corruption issues somehow. I still do not know why. In initially panicking I had thought that this may be the final straw for Bullet and proceeded to look at alternatives: PhysX and ODE. This however proved to be instantly problematic: as it turns out PhysX also does not support dynamic builds and could cause the exact same issues. ODE did support dynamic builds but was considerably dated and did not have much documentation.

It was at this point that I realised that I had already solved the problem: all I had to do was substitute the alternate functioning project files for the existing broken ones. This was simply a matter of switching out the files and keeping the git folder locally. I tested this initially in a separate branch and I will merge the main branch starting early in the next week.

The one thing that still bothers me is why the old project does not work, the only answer I can think of is the one thing which changed, that being our project files and solution. The CRT can change with these files and, hypothetically, this would cause the issues we saw. I will however have to leave this unanswered for now.

This encompassed the majority of my time this week, and in all honestly was the biggest hurdle the project has faced so far.