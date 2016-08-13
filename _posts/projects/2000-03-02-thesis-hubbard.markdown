---
layout: post
reponame:  thesis-hubbard
title: Exact diagonalization of the Hubbard model implemented in Python
githuburl: https://github.com/PedroMDuarte/thesis-hubbard
date: 2000-03-02 00:00:00
modified:   2014-09-04 04:09:16 
created: 2014-09-02 01:01:51 
languages: Python, NumPy
keywords: hubbard model, exact diagonalization
summary: Exact diagonalization solutions of the Hubbard model implemented in python.
zenodobadge: <a href="http://dx.doi.org/10.5281/zenodo.11558"><img src="https://zenodo.org/badge/doi/10.5281/zenodo.11558.svg" alt="10.5281/zenodo.11558"></a>
categories: toptier, gradschool
---

In my PhD experiment I experimentally studied ultracold atoms in 3D optical
lattices consisting of about 40x40x40 lattice sites. When you are thinking
aobut such system it is helpful to have a good understanding of what happens in
a system of just a few lattice sites, say 1x2 or 2x2. 

Solutions can be readily obtained for such small systems; however, it is
remarkable that systems with more that just a few tens of particles are
intractable even for the most powerful computers known to humanity (the problem
scales exponentially both in time and space with the number of lattice sites).

In any case, to build up my intuition about what cold atoms do when moving in a
lattice, I implemented this exact solver.  You can run it for small systems.
The algorithm itself scales for an arbitrary number of particles, but if you
try to run it for more than just a few your computer will not be happy.  

**For the physics enthusiasts:**

Here I present code to develop the solutions for treatments of the Hubbard
model, including: 

- t=0,  single-site approximation
- exact diagonalization for a 1x2 lattice
- exact diagonalization for a 2x2 lattice 

Both of the exact diagonalization codes assume half-filling and an equal number
of spin up and spin down particles. The 2x2 code can be generalized for 3D
lattices of arbitrary sizes, however not a lot of testing
has been performed for systems above 1x2x2.

For a quick glimpse, check out the code for the arbitrary size solution
[here](https://github.com/PedroMDuarte/thesis-hubbard/blob/master/exactdiag_4site2particles/fh.py).

Be warned, do not try to run the code for more than a handful of lattice sites.
The problem scales exponentially both in time and space with the number of
lattice sites! That's why I had to build an [analog quantum
computer](http://bit.ly/afm-nature) to try and shed some light to the understanding of these systems. 


