---
layout: post
reponame:  thesis-hubbard-lda_evap
title: Optimizing the design parameters of an optical lattice potential
githuburl: https://github.com/PedroMDuarte/thesis-hubbard-lda_evap
date: 2000-03-03 00:00:00
modified:   2014-09-18 15:46:28 
created: 2014-09-17 20:47:31 
languages: Python, NumPy, SciPy
keywords: parameter tuning, grid search, optical lattice, evaporative cooling, local density approximation
summary: Local density approximation implementation for the Hubbard model in a finite inhomogeneous lattice potential.
zenodobadge: <a href="http://dx.doi.org/10.5281/zenodo.11761"><img src="https://zenodo.org/badge/doi/10.5281/zenodo.11761.svg" alt="10.5281/zenodo.11761"></a>
categories: toptier, gradschool
---

As I have mentioned before, the goal of my PhD research was to collect some
atoms in a light trap and make them as cold as possible.  To decide on the
parameters that we were going to use for the geometry of the trap, we had to
study a very important figure of merit: evaporative cooling. In other words we
need to answer the question, would the hottest atoms be able to escape our
potential (thus leaving the remaining ones at a colder temperature)? 

When your collection of atoms is near absolute zero, this question is not so
easy to answer.  The numerical calculations available in this repository
implement a treatment that is mostly valid at very low temperatures, and at the
same time is computationally cheap to evaluate.   Computational cost is key
when we want to do a grid search over the available parameter space (and we
don't want it to run for several days).  

**For the experts:**

The local density approxmation (LDA) is used to obtain spatial profiles of all
relevant potentials and thermodynamic quantities in a compensated optical
lattice.  In order to achieve fast iteration on the optimization for the trap
parameters, we used the high-temperature series expansion (HTSE) up to second
order in $T/t$ as a solution to the homogeneous system.  The local density
approximation stitches together a bunch of local homogeneous solutions to
produce spatial profiles of physical quantities. 

The resulting LDA profiles are used to analyze different values of the
parameters of the compensated lattice setup in order to compare advantages and
disadvantage of different kinds of traps.

For a quick glimpse at how this code can be used, check out [this IPython
notebook](https://github.com/PedroMDuarte/thesis-hubbard-lda_evap/blob/master/ldaEvaporation.ipynb)
and also [the code that implements the trap paramter
optimization](https://github.com/PedroMDuarte/thesis-hubbard-lda_evap/blob/master/optevap.py). 
