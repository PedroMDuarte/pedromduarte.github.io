--- 
layout: post
title:  "Enterprise Software with Python"
date:   2016-07-10 10:37:49
categories: journal python
---

I started going through this series of training videos by Mahmoud
Hashemi. I will include some comments on each of the sections of the
course below, both to help me remember what I learned and to maybe
motivate others to take the course themselves.

### 1. Debunking some myths about Python

The first section in the course is about why Python can be a good option for
enterprise software, even though some people don't perceive it that way. A very
good reference for this kind of material is Hashemi's blog post: [10 Myths of
Enterprise
Python](https://www.paypal-engineering.com/2014/12/10/10-myths-of-enterprise-python/).

In this section, Mahmoud also does a very good job in giving his definition of
what is enterprise software. The bottom lime is that *enterprise software* is a
term that gets thrown around a lot, and that it is not a black and white
concept. 9 different dimensions or aspects of enterprise software are explained
in detail, and the discussion is useful to think about the different kind of
requirements that your software will need to satisfy, depending on its purpose.

### 2. Software architecture (with Python)

This section is all about considerations that you should take before
starting to work on a particular project.  I wrote "with Python" in
parenthesis, because most of the advise here is very general, and not
just for Python projects.  The emphasis is in understanding the
requirements of your customers, knowing very well the environments you
will be working on (and their limitations), and choosing your
dependencies carefully.

The goal of these considerations is to be able to come up with a
final product that is pleasant to use by the customers and that is
easy to maintain by the developers.  Mahmoud stresses out the fact
that you don't want to spend all your time maintaining past projects.
You want them to be robust so that you are able to move on to the
next thing without worrying much about maintaining past projects.

As an experimental physicist I completely identify with the above concept.
When building complex scientific apparatus, every step along the way must be
nearly maintenance free, so you can move up the complexity ladder and get to
the point where your machine can create conditions that have never been studied
previously. 

In addition to ease of use and maintainability, Mahmoud talks a
little bit about how to navigate the organizational and interpersonal
challenges that may occur when working on enterprise software.  He touches on
some very real situations that one may encounter at work.  I liked learning how
some of these concepts have been given proper names in the software community,
such as [bike-shedding](https://en.wikipedia.org/wiki/Law_of_triviality) or the
[queen's duck](http://blog.codinghorror.com/new-programming-jargon/).  

As a person that is sometimes a little bit obsessive, I made good note of all
of Mahmoud's comments during this section, and I have tried to apply them at
work as much as I can.  Being aware of your social skill level can only help
improve it. 


### 3. Best practices

This section starts out talking about editors and development tools. Mahmoud
goes over the options that you can choose from as far as IDE's, editors, and
other development tools. I particularly like his advice to keep autocompletion
off.  This allows you to practice constantly in the kind of environment that
you will find, say, in a production server, that is not configured and loaded
up with all the goodies that you may have in your laptop. In this section there
are also some very good discussions regarding source control, issue tracking,
and continuous integration.

At this point the course becomes more hands-on, as Mahmoud starts showing you
how to go through the typical steps you will find yourself doing when creating
a Python project from scratch. The examples are shown directly at the console
and on the github website, so this part was very illustrative.

In this section, which makes up the bulk of the course Mahmoud covers topics
like debugging, security, testing, logging, profiling and packaging.  For all
of these he gives some general pointers and then goes into detail as to how
these topics present themselves at his organization (Paypal).   

A lot of the content in this section is an excellent starting point for doing
more research on a particular topic.  I have already come back to parts of this
section.  Specifically the other day I wanted to profile a script I was working
on to process some time series data, and the first think I did was go back to
the videos and get a quick review before digging further into the internet. 

### 4. Next steps

The course sends you off in a very positive note, encouraging you to continue
building your python skills and pointing you to various possible ways in which
you can do so.

Overall this course is great!  Mahmoud's goal is not to hold your hand while he
works you through some example, his goal is to make you feel curious and give
you a head start when you start looking at the details of a specific topic on
your own.  In that regard he has done a great job.  I can see myself going back
to this material many times in the future. 


