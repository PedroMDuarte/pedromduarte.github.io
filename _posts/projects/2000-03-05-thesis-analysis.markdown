---
layout: post
reponame:  thesis-analysis
title: Processing images of ultracold atom clouds
githuburl: https://github.com/PedroMDuarte/thesis-analysis
date: 2000-03-05 00:00:00
modified:   2016-01-11 02:15:51 
created: 2014-09-17 20:40:58 
languages: C++, GNU Scientific Library, Python, SciPy
keywords: atom cloud microscopy, eigenface, non-linear regression
summary: Analyze density profiles of ultracold Fermionic gases
zenodobadge: <a href="http://dx.doi.org/10.5281/zenodo.11760"><img src="https://zenodo.org/badge/doi/10.5281/zenodo.11760.svg" alt="10.5281/zenodo.11760"></a>
categories: toptier, gradschool
---

Atom cloud distributions are obtained from the shadow that they cast on a laser
beam projected onto a CCD camera.  We collect pixel data for two separate
images: a reference shot (no atoms present) and an experiment shot (atoms
present).  We use linear least-squares to generate the linear combination of
recent reference shots that most closely approximates the background in the
experiment shot. This technique is known as the eigenface method, due to its
similarity to the well-known face image classification method.

After subtracting the background,  we reconstruct the atom density from the
measurement of light scattered by the atoms (this dependes on some parameters
like the magnetic field the atoms are in, and the polarization, detuning, and
power of the probe light, among others).

The reconstructed density distribution is fitted to a theoretical distribution
to extract physical quantities (size, temperatuare) of the atom cloud.  The
non-linear regression code is written in C++ using the GNU Scientific Library.
Function evaluation loops were parallelized using openmp. 

Using the C++ implementation and openmp we were able to reduce the fitting time
to only a few seconds, compared to several minutes for the same algorithm
previously implemented in numpy/scipy.

