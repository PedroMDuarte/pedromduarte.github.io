---
layout: post
reponame:  hubbard-lda3
title: Measuring the temperature of ultracold atoms held in an artifical light crystal
githuburl: https://github.com/PedroMDuarte/hubbard-lda3
date: 2000-03-04 00:00:00
modified:   2014-12-02 03:31:56 
created: 2014-11-19 16:46:35 
languages: Python, NumPy, SciPy
keywords: hubbard model, local density approximation
summary: Implementation of the local density approximation leveraging state-of-the art results for an homogeneous Fermi-Hubbard model.
zenodobadge: <a href="http://dx.doi.org/10.5281/zenodo.12780"><img src="https://zenodo.org/badge/doi/10.5281/zenodo.12780.svg" alt="10.5281/zenodo.12780"></a>
categories: toptier, gradschool
---

My PhD research consisted of suspending atoms in 3D arrays of light pockets,
also referred to as optical lattices. We cooled the atoms near absolute zero
temperatures, to get them to exhibit some interesting quantum mechanical
behavior.  However, the atoms were so cold that it was hard to even measure
their temperature. 

In [an article published in Nature](http://bit.ly/afm-nature), we demonstrated
that we could use the effect of the atoms on a weak pulse of light shined at
them, along with the numerical calculations presented here, to get an idea of
how cold the atoms really were. 


**For the experts:**

The local density approximation (LDA) allows calculation of spatial profiles of
thermodynamic quantities by stitching together calculated values for a
homogenous Fermi-Hubbard model.  In this code we implement a way of stitching
together Quantum Monte Carlo results (provided by Thereza Paiva) and  Numerical
Linked Cluster Expansion (NLCE) results (provided by Ehsan Khatami), in order
to calculate trap profiles for the conditions realized in our experiment.

The combination of experimental data (obtained in my PhD experiment) and the
theoretical imput from the LDA (as implemented by me here) have helped realize
the first [spin-sensitive scattering thermometer for atoms in optical
lattices](http://bit.ly/afm-nature).  Prior to this work, measuring the
temperature of ultracold atoms in optical lattices was limited to temperatures
about 3 times as large as what we achieved. (Incidentally, we achieved a
temperature of 32 nano-Kelvin in our experiment, about 1.5 times larger than
the Neel temperature, at which the system fully orders itself
antiferromagnetically). 

For a more detailed explanation of how the LDA was implemented, refer to
Appendix B in my [PhD thesis](http://bit.ly/pmd323thesis). 
