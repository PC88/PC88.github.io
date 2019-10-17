---
title: AMGs a glance to another science
excerpt: Some insights on AMGs
author: Peter Cannon
categories:
  - topics
  - Data Science Collaboration Project
background-image: DNAmage.jpg
#date/lastmod are optional
#date: 2019-10-17 17:09:46 +0100
#lastmod: 2019-10-17 17:09:46 +0100
---

<hr />

## AMGs an initial understanding: Post 1

As stated in an earlier post I feel that understanding the genetics and various other aspects of marine science is not necessary but would help undoubtedly on the data science end. To that effect I have studied the papers of the following:

Breitbart, M., Thompson, L., Suttle, C. and Sullivan, M. (2007). Exploring the Vast Diversity of Marine Viruses. *Oceanography*, 20(2), pp.135-139.

Nissimov, J., Pagarete, A., Ma, F., Cody, S., Dunigan, D., Kimmance, S. and Allen, M. (2017). Coccolithoviruses: A Review of Cross-Kingdom Genomic Thievery and Metabolic Thuggery. *Viruses*, 9(3), p.52.

Coming from a background of computer science, it was initially quite a challenge to unravel many of the acronyms and scientific jargon used in the above papers, however I was able to garner some interesting insight even as layman in this area, the following is a discussion on what I feel I learned and an expanded explanation that any reader might also understand what I have from these papers. I will conclude with some of the insights I have learned from them which may prove fruitful in the search for more avenues for data science in the domains of AMG`s and marine viral communities.

Starting with:

Breitbart, M., Thompson, L., Suttle, C. and Sullivan, M. (2007). Exploring the Vast Diversity of Marine Viruses. *Oceanography*, 20(2), pp.135-139.

This paper was far easier to understand than the later, and does lend a significant overview in to what AMGs are so what are AMGs?

<hr />

## what are AMGs

AMGs or auxiliary metabolic genes are the genes to what larger, more evolved forms of life use for core systems in their genetic biology. These being those of photosynthesis to extract vital energy to continue life, make other genetic and biological systems run, and improve their production capacity and speed.

The fact that these genes are present in namely more evolved forms of life is a key tenant here. Some papers will refer to these genes as "host" genes, as they are generally genes which are held by biological organisms which play hosts to viruses -- such as many of the viruses which will be discussed here. The reason for this is simple and yet disingenuous: "host" genes are genes which were thought exclusively to play the role in using the genetic systems built up in more evolved forms of life: that of the host, and not the smaller less evolved viruses. Yet as shown in the above papers the premise of this is some what false, as these genes are found presently in these lower level organisms such as the cyanophages (Chen and Lu, 2002; Mann et al., 2005; Sullivan et al., 2005).

The question now is why?

The why of the matter is a very interesting topic. The reason for the presence of these genes is simple and yet revolutionary in terms of our understanding of viruses and of the domains of life. In order to understand this aspect, I will diverge on a tangent which I hope will make understanding this far easier to anyone who was in the position of myself not all that long ago:

<hr />

## Phylogeny, and what its implications are.

In the other more intense paper, I studied:

Nissimov, J., Pagarete, A., Ma, F., Cody, S., Dunigan, D., Kimmance, S. and Allen, M. (2017). Coccolithoviruses: A Review of Cross-Kingdom Genomic Thievery and Metabolic Thuggery. *Viruses*, 9(3), p.52.

It explorers the commonalities between thirteen different strains of coccolithovirus. As implied in the title the coccolithovirus is a genetic thief and a metabolic thug, in the perhaps more literal sense than one may imagine. This brings us to a topic called "Phylogeny".

Phylogeny is the evolution of a genetically related group organisms via the study of the protein or gene evolution by having the comparison of homologous sequences.

What this means to us laymen is that thing which have aspects of similar phylogeny have a cross biological set of genes, or for a better way of understanding: we share genetic code with many other creatures at various other levels of life, and in different domains of life. This makes a lot of sense when you thin about it, but perhaps more in light of all that thuggery and thievery I mentioned earlier, so back to it:

The reason the coccolithovirus is both a genetic thief and metabolic thug is because when a virus infects a host, they each take a little piece of each other. This is the process known as horizontal gene transfer. So, we know why it's a genetic thief but why a metabolic thug? Simple, once the virus has these pieces of genetic code from its host, it has a very literal "key" to its genetic lock. The example of this is clear is cocclithovriuses and host cyanobacterium. The cocclithovriuses through many millions of horizontal gene transfers have eventually been able to get a hold of the genetic key for photo synthesis in its host. It can now unlock the photosynthetic cells in its host and intimidate them (thugs mind you) to make more of its self, using the hosts own systems to create more of its self.

Now we know the means and motive in the dramatic case of the stolen genes: horizontal gene transfer, and good old self-preservation.

This does lead to a very interesting set of observations which I can now say I understand. If viruses and hosts can steal genes and then bend both to their own devices what does this mean for various types of life, and how does this transcend the barrier of the three domains of life: Eukarya, Bacteria and Archaea?

Most importantly what does that mean for me and my desires for data science? This once again is best explained through a tangent which I hope any person will come to understand.

<hr />

## Eigen Values, and an old lock with an evolving key.

Although the title of this section may seem daunting my goal is to make anyone who reads this understand it by the end. As a student of computer science generally, and computer game technology specifically I have been known to venture in to the field of mathematics from time to time. Mathematic which many people regard as the devil is really the study of abstraction, whether you know it or not you have used abstraction in its many forms as abstract things can be used to describe may concrete things. In software engineering I make an abstract thing inherit down to concrete instantiations. The classic example which anyone can under stand is that in life we have animals, and mammals and reptiles are "types" of animals. Now mammals and reptiles both retained mouths, so that's in a sense a genetic piece of code which each type of creature has hung on to but if we take this a little further:

As mentioned earlier the three domains of life are scientifically: Eukarya, Bacteria and Archaea;

Eukarya being:

"any member of a domain of organisms having cells each with a distinct nucleus within which the genetic material is contained. Eukaryotes include protoctists, fungi, plants, and animals Compare prokaryote."

Bacteria:

"a member of a large group of unicellular microorganisms which have cell walls but lack organelles and an organized nucleus, including some which can cause disease."

And lastly Archaea:

"microorganisms which are similar to bacteria in size and simplicity of structure but radically different in molecular organization. They are now believed to constitute an ancient group which is intermediate between the bacteria and eukaryotes"

So, if we know that every form of life falls under these categories and we know that they all evolved for as old as life is, while stealing, sharing, infecting and elsewise intimidating each other's genes. We might understand that the more successful forms of evolution remain, they are in a sense the bits we keep. The bits we keep and often the most integral to our functions: the Auxiliary Metabolic Genes or AMGs.

To close out the maths and that strange term in the title "Eigen Value", in maths an Eigen Value is a value which keeps its form over a series of transformations. We are looking for a genetic Eigen Value which evolution has kept across its many transformations, which these viruses we suspect are using in their evolution to overcome our genetic code which remains the same, because if they get the key to the piece of code which has remained there for many generations (that Eigen value) its more integral and core to that organism. This genetic code we keep is the old lock, and their repeated attempts to try it is the evolving key. This is shown in the very way virus genetic evolve from the first paper:

"65%-95% of marine viral metagenomic sequences are not similar to previously described sequences, as opposed to cellular metagenomic surveys."

Which does leave us with a dilemma. These viruses and lower level organisms rapidly iterate, they live for far less on average than that of a human -- a Eukarya. Thus, the generate genetics on a more rapid rate as they reproduce orders of magnitudes more than us. Which means that the pieces which remain the same can be hard to track down as they constantly change and evolve. To further complicate matters certain viruses are not so simple, DNA is typically used for higher level organisms, so viruses usually contain RNA, RNA is like a lower level DNA for other organisms. Now RNA and DNA are things that evolve and could be targeted if they are isolated, so if all viruses just had RNA and we found some genetic trend in RNA we could gain a great understanding of these viruses. With that said not all viruses remain on this lower level. Epstein-Barr virus for example does in fact have DNA so a one size fits all approach is not effective even at this level. However, there is parts which do remain the same and can be targeted for research and promise insight.

<hr />

## Its not all that simple a human parallel: HIV and the bubonic plague.

Now it would be fun if I could simply say now, I must analyse data for some insights in to this lovely nice to describe lock and key and all would be well and good, but alas life is not that simple. This is shown through humanities struggle with disease and how our evolution has moulded us: hence the mention of HIV and the black plague.

The black plague devastated all of Europe from the years of 1347 to 1351 it killed millions of us somewhere between 75 million and 200 million people. It then reoccurred in the late 17th century and went through the Balkans multiple times. What does this have to do with anything you may ask? Well that lock and key I mentioned, the lock evolves evolution as well took note of the disastrous success of this disease in the Balkans and as a result, unlike many people in other areas of Europe who were only hit once by the plague, their genes removed the receptor for the black plague. That piece of genetic material which allowed the plagues so deadly key to work. This same receptor CCR-5 is the same receptor which allows HIV so to spread, so with one fell swoop humanity changed the locks and they evolved too.

What this means is that as life iterates and moves, it evolves on both ends if we garner one insight it might change in future, which is why we should be looking for the patterns which remain the same across life in genetics as the longer it carried across the more effective it is. This area of science has no lack of complexity even from my cursory glance and I will try to keep that in mind as I pursue the topic further.

So, what we can say from the above remarks: viruses turn AMGs against their hosts to make them self's more effective, therefore the contain elsewise useless genetics across many iterations as shown by the photosynthetic genetics in a lifeform which has no photosynthetic cells. How they gain access to these cells functions is through being at some form in the past evolution at the same genetic level as higher evolutions of life, thus we both at some point over the millennia of phylogeny contained the same abstract genetic information which allows viruses to invade and take genetic material giving them access to AMGs.

<hr />

## conclusions

In summary the papers here and some other research has shown me that my data science skills should initially be aimed at finding a gene sequence which stays the same across many rapid iterations of viruses. As with the Coccolithoviruses these will lend insight in to the trends of these organisms behave in their eco system and perhaps shed some light on our own, as the section on the plague shows the mirrored effect of human biology.

This has given me a very interesting insight in to this field and I feel already will aid me in the next chapter of this project where I will look at how I can move this new-found knowledge, in to data science.

I look forward to research on on exactly that, and will continue this blog as I progress.
<hr />