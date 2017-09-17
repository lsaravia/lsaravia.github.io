--- 
title: "Multiespecific neutral/hierachical stochastic spatial model"
date: 2016-11-18
comments: true 
categories: 
- github 
- Stochastic spatial models  
- Neutral theory
- Hierarchical competition
---

This is C++ code for neutral/hierarchical competition models available at <https://github.com/lsaravia/Neutral>
. In this model all species have the same parameters except the probability of colonization from metacommunity. More details are given in the file ModelDescription.md

There are actually 5 similar models built in

* Non-saturated neutral (Etienne 2007)
* Saturated Neutral
* Non-saturated Hierarchical (Tilman 1994)
* Saturated Hierarchical
* Continuum model between 2 and 4 (or 1 and 3)

And three dispersal kernels

* Uniform
* Exponential
* Inverse power

It was compiled using Gnu C++ (g++ v4.8.5). For a crude and slow graphical output you will need the X11 SDL development libraries and the GRX graphics library http://grx.gnu.de/grx246um.htm

You also need the code from:

<https://github.com/lsaravia/mfsba> if you want the multifractal spectra output otherwise you have to comment the calls to the function MultifractalSBA and the includes to mf.h header.
<https://github.com/lsaravia/Clusters> to calculate cluster statistics.

To compile under Windows there is a separate makefileWin.mak, you might have to modify the folders of the mfsba and Clusters sources.

The folder R has functions to interface R with the model

## Citation

If you use the model please cite one of the following:

Saravia, L. A., & Momo, F. R. (2017). Biodiversity collapse and early warning indicators in a spatial phase transition between neutral and niche communities. Oikos. https://doi.org/10.1111/oik.04256

Saravia, L.A. (2015). A new method to analyse species abundances in space using generalized dimensions. Methods Ecol. Evol., 6, 1298–1310

Saravia L.A. (2014) Neutral: A sofwtware to simulate spatially explicit neutral/hierarchical models. <http://dx.doi.org/10.6084/m9.figshare.969692>.


## Bibliography

Tilman, D., 1994. Competition and biodiversity in spatially structured habitats. Ecology, 75(1), pp.2-16.

Etienne, R.S., Alonso, D. & McKane, A.J., 2007. The zero-sum assumption in neutral biodiversity theory. Journal of Theoretical Biology, 248(3), pp.522-536.

