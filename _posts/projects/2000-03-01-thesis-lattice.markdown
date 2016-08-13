---
layout: post
reponame:  thesis-lattice
title: Band structure calculations for an optical lattice implemented in Python
githuburl: https://github.com/PedroMDuarte/thesis-lattice
date: 2000-03-01 00:00:00
modified:   2014-09-05 11:42:35 
created: 2014-09-05 11:30:03 
languages: Python, SymPy, NumPy
keywords: optical lattice, band structure, hubbard model
summary: Band structure calculations for an optical lattice 
zenodobadge: <a href="http://dx.doi.org/10.5281/zenodo.11612"><img src="https://zenodo.org/badge/doi/10.5281/zenodo.11612.svg" alt="10.5281/zenodo.11612"></a> 
categories: toptier, gradschool
---

For a quick glimpse at what this code does, check out [this IPython notebook](https://github.com/PedroMDuarte/thesis-lattice/blob/master/BandStructure.ipynb)

The calculation of a band structure is a problem presented to most
undergraduate physics students around their 3rd or 4th year.  As usual one
encounters some subtleties when actually trying to calculate numerical results
for a realistic situation. 

This code implements (in Python) the band structure calculation for a
sinusoidal periodic potential (a very good approximation to an optical lattice)
in up to three dimensions.

**For the physics enthusiasts**

Here I present code to construct the single particle eigentstates in a
sinusoidal potential, such as that created by an optical lattice. We define
methods to calculate the band structure and implement interpolation functions
of the obtained results to speed up subsequent calculations.  The Wannier
states in the lattice are constructed starting from the eigenstates of the
Hamiltonian.  The tunneling matrix element and the on-site interaction energy
(relevant for the Hubbard model) are calculated. <br>


