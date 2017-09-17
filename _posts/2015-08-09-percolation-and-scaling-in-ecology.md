---
title: "Percolation and scaling in ecology"
date: 2015-12-26 10:30
comments: true
categories: 
- Percolation 
- Scaling
- Ecological theory
- Ecology
---

Scaling is a central theme in ecology, well this is my opinion, but there are others that think like me, for example Brian Enquist, that organized a symposium for the 100th anniversary of the Ecological Society of America [Scaling in Ecology](https://brianjenquist.wordpress.com/2015/02/02/scaling-in-ecology-and-the-esa-100th-anniversary-symposium-on-a-focus-on-scaling-for-the-next-100-years). He mentioned that two of the most influential papers from ESA were about scaling:  [Simon Levin The Problem of Pattern and Scale in Ecology](http://www.esajournals.org/doi/abs/10.2307/1941447) and [J.H. Brown The Metabolic Theory of Ecology](http://www.esajournals.org/doi/abs/10.1890/03-9000). But why some
processes permeate through scales and others do not; scaling is important because it implies something that crosses scales, did you ever heard the phrase: think globally act locally. Our new preprint analyzes what happens when [one species percolates through the landscape](https://peerj.com/preprints/1589/)

<!-- more -->


Think globally, act locally has been extensively used in environmental campaigns about earth health; and it is precisely about scaling, about the spread of something trough scales: local actions that have a global effect. In fact we don't know which are the effect of most local actions on a global scale, this is a social issue that is very interesting and is in the line of the plenary talk given by Simon Levin (which I knew by twitter thanks to @DrEmilySKlein) 

> @DrEmilySKlein https://twitter.com/DrEmilySKlein 
>
> - Dr Levin: So the challenge is - how do we look towards sustainability? Can we look up macroscopic patterns and emergent properties? #ESA100
>
> 

> @DrEmilySKlein https://twitter.com/DrEmilySKlein 
> - Dr Levin: Collective action is possible if you build up from smaller scales and individual actions #ESA100
 

> @DrEmilySKlein https://twitter.com/DrEmilySKlein 


> - @DrEmilySKlein: Dr Levin: Linking these ideas of econom theory,scales,individual action,possibility of collective action = imp for managing Commons #ESA100


I wanted to talk about percolation, percolation is something you can experience when you filter coffee, soluble substances in coffee grains pass through the filter and make the beverage that we drink. The theory about percolation has expanded from the fluid of liquid in porous media to a lot of different fields including biology and ecology. There are excellent introductions in the context of ecology like this: [Survival of species in patchy landscapes: percolation in space and time](http://beata.web.elte.hu/Scaling-Chapter.pdf) even some lectures by well a known author in the field [Shlomo Havlin](http://havlin.biu.ac.il/course3.php). Basically percolation is a threshold phenomena: it happens when due to a local interaction (I mean the connection between two neighbours) some kind of message or process spreads to all scales, and this happens suddenly at a critical point. 

I started to study this in the context of community ecology: can you think about what happens if one species percolates? there is a patch of one species that connects the landscape. What are the consequences for diversity?, when we can observe percolation in a community? 

I made a spatial model to study the transition between neutral and niche communities <https://github.com/lsaravia/Neutral>, when the community has no interactions it is in has a neutral dynamics. But if individuals start to have competitive interactions, best competitors start to replace bad ones and with increasing intensity of competition there is a point were one species percolates, spreads from side to side of the simulation arena. This is a critical point because there is a sudden change in the proportion of this species and as a consequence it produces a biodiversity collapse.  Here is an animation of the transition:

![Animation of transition]({{ site.url }}{{ site.baseurl }}/assets/images/neuU32_256R0.0029.gif)

What happens in this animation:

* When a species patch spreads from one side to the other of the landscape it percolates, and I change the color of the other accompanying species in the animation, so the image becomes bi-color: the pink pixels are the accompanying species and the brown pixels the percolating species.

* The size of the biggest (**Size**) patch that will be the spanning patch goes from 0.14% ---in proportion of the landscape--- to approximately 0.60%.

* The Shannon diversity (**H**) drops from 1.75 to 1.45 

* The richness (**S**) keeps more or less the same

Percolation has a low probability to happen in a purely neutral model, in my model has a zero probability but that depends on the metacommunity's species abundance distribution, because on the long term the local community tend to be equal to the metacommunity in species abundances. When the community have a small probability of competitive interactions percolation is the rule. In the previous animation the probability of a competitive displacement between two interacting individuals was 0.0011, so it is very low. 

This kind of critical behavior should be observed when climatic conditions or stress change, thus I am looking for data on communities that change its competitive behavior when suffer some stress to validate that this happens in real communities. 

One interesting thing about this critical transition is that happens well before the communities start to loss cover, or before there is any habitat loss, so we could have an early warning signal detecting percolation. 


More about this in our preprint [Biodiversity collapse in a phase transition between neutral and niche communities](https://peerj.com/preprints/1589/)
