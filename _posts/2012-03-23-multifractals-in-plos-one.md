---
title: "Multifractals in PLoS ONE"
date: 2012-03-23T22:30:00-07:00
comments: true
categories:
 - ideas
 - periphyton
 - multifractals
 - landscape ecology
---

We have just published a paper about ecological succession and multifractals and I like it:

[Multifractal Spatial Patterns and Diversity in an Ecological Succession](http://dx.plos.org/10.1371/journal.pone.0034096)

I played around with some of the features of PLoS web, and we are the one of a few papers (4) published in PLoS with the keyword  “multifractal” in the abstract. I feel I am not alone in the world. 

again I used my open source software

<https://github.com/lsaravia/mfsba>

Besides it is not discussed enough in the paper, this is about comparing different landscapes using multifractals. And one of the drawbacks of the method is that you need several images to compare  different situations. I am thinking of improving it to include the case of one image for each situation. ¿How this can be done? Using bootstrapping to obtain confidence intervals around generalized dimensions $D_q$. Another, much easier, improvement would be to report maximum likelihood estimators of $D_q$ along with the ones obtained by linear regression.

