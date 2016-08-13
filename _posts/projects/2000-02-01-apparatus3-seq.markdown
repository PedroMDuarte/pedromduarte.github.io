---
layout: post
reponame:  apparatus3-seq
title: Time sequence generator for cold atom experiments
githuburl: https://github.com/PedroMDuarte/apparatus3-seq
date: 2000-02-01 00:00:00
modified:   2016-01-18 07:12:23 
created: 2012-03-04 22:54:06 
languages: Python
keywords: experiment control, sequence generator 
summary: brief summary goes here 
categories: toptier, gradschool
---

This was one of my first projects when I joined the [atom cooling
group](http://atomcool.rice.edu) at Rice University.  Even though I did not
have much experience with cold atom experiments at the time, I am proud to
say that the initial design of the program passed the test of time with flying
colors.  The core component of this project is the file called
[seq.py](https://github.com/PedroMDuarte/apparatus3-seq/blob/master/seq.py),
it defines the seq class, which allows the experimenter to abstract the concept
of a timing sequence and play around with it at will. This includes any kind of
arbitrary modifications on a set of digital channels, and also triggering of
analog wafeforms at specific points in time. 

Around the simple seq.py abstraction we were able to construct very complicated
experimental sequences, and also we were able to separate different stages of the 
experiment completely such that in our heads we would only need to keep the
details of the particular step we were working on optimizing at any given time.

The two other experiments in our lab ended up ditching their control systems
and adopting seq.py due to its versatility and ease of use. 

