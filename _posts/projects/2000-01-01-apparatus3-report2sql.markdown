---
layout: post
reponame:  apparatus3-report2sql
title: Moving data from a collection of INI files to a MySQL database
githuburl: https://github.com/PedroMDuarte/apparatus3-report2sql
date: 2000-01-01 00:00:00
modified:   2013-10-28 00:25:55 
created: 2013-10-27 06:38:09 
languages: Python, SQL
keywords: keep my sanity when querying experiment data
summary: brief summary goes here 
categories: toptier, gradschool
---

The parameters used and high-level results obtained for each run of my PhD
experiment were stored in an INI file.  We ran the experiment a few thousand
times per week for over 3 years.   When I started to run into bottlenecks where
querying the set of all INI files would take forever, I decided to dump all the
data into a database.  This was mostly an excuse to learn about SQL and
relational databases, but it also was of great help when trying to locate old
data runs and find similar sets of runs over a large period of time.  

