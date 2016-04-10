---
layout: post
title:  "Stat Learning - Model Selection in R"
date:   2016-04-10 10:37:49
categories: stat-learning
---

Notes from the R session for Chapter 6 in the course: Linear Model Selection and Regularization.  Using validation and cross-validation for selecting the tuning parameters in stepwise regression, Lasso, and Ridge Regression. 

<!-- Example of code highlighting for R
{% highlight r %}
{%endhighlight %}
-->

{% highlight r %}
library(ISLR)
summary(Hitters)
{%endhighlight %}

There are missing values in the data so eliminate every row in the data that has a missing value, by using the `na.omit` function: 

{% highlight r %}
Hitters = na.omit(Hitters)
{%endhighlight %}

### Best subset regression

Will use the  `leaps` package to run a model regression on Salary, considering all the other variables in the data set as possible predictors.  

The function `regsubsets` will do an all subsets regression.  In this case there are 19 predictors, so the all subsets regression will default to subsets with up to 8 predictors only:


{% highlight r %}
library(leaps)
regfit.full = regsubsets(Salary~.,data=Hitters)
summary(regfit.full)
{%endhighlight %}

{% highlight r %}
Subset selection object
Call: regsubsets.formula(Salary ~ ., data = Hitters)
19 Variables  (and intercept)
           Forced in Forced out
AtBat          FALSE      FALSE
Hits           FALSE      FALSE
HmRun          FALSE      FALSE
Runs           FALSE      FALSE
RBI            FALSE      FALSE
Walks          FALSE      FALSE
Years          FALSE      FALSE
CAtBat         FALSE      FALSE
CHits          FALSE      FALSE
CHmRun         FALSE      FALSE
CRuns          FALSE      FALSE
CRBI           FALSE      FALSE
CWalks         FALSE      FALSE
LeagueN        FALSE      FALSE
DivisionW      FALSE      FALSE
PutOuts        FALSE      FALSE
Assists        FALSE      FALSE
Errors         FALSE      FALSE
NewLeagueN     FALSE      FALSE
1 subsets of each size up to 8
Selection Algorithm: exhaustive
         AtBat Hits HmRun Runs RBI Walks Years CAtBat CHits CHmRun CRuns
1  ( 1 ) " "   " "  " "   " "  " " " "   " "   " "    " "   " "    " "  
2  ( 1 ) " "   "*"  " "   " "  " " " "   " "   " "    " "   " "    " "  
3  ( 1 ) " "   "*"  " "   " "  " " " "   " "   " "    " "   " "    " "  
4  ( 1 ) " "   "*"  " "   " "  " " " "   " "   " "    " "   " "    " "  
5  ( 1 ) "*"   "*"  " "   " "  " " " "   " "   " "    " "   " "    " "  
6  ( 1 ) "*"   "*"  " "   " "  " " "*"   " "   " "    " "   " "    " "  
7  ( 1 ) " "   "*"  " "   " "  " " "*"   " "   "*"    "*"   "*"    " "  
8  ( 1 ) "*"   "*"  " "   " "  " " "*"   " "   " "    " "   "*"    "*"  
         CRBI CWalks LeagueN DivisionW PutOuts Assists Errors NewLeagueN
1  ( 1 ) "*"  " "    " "     " "       " "     " "     " "    " "       
2  ( 1 ) "*"  " "    " "     " "       " "     " "     " "    " "       
3  ( 1 ) "*"  " "    " "     " "       "*"     " "     " "    " "       
4  ( 1 ) "*"  " "    " "     "*"       "*"     " "     " "    " "       
5  ( 1 ) "*"  " "    " "     "*"       "*"     " "     " "    " "       
6  ( 1 ) "*"  " "    " "     "*"       "*"     " "     " "    " "       
7  ( 1 ) " "  " "    " "     "*"       "*"     " "     " "    " "       
8  ( 1 ) " "  "*"    " "     "*"       "*"     " "     " "    " "        
{% endhighlight %}

In the output shown above, the `n`th row represents the best `n` parameter model.  The asterisk in double quotes indicates if a predictor is part of the model.

We can also tell `regsubsets` to get all subsets up to 19 predictors:

{% highlight r %}
regfit.full = regsubsets(Salary~.,data=Hitters, nvmax=19)
reg.summary=summary(regfit.full)
plot(reg.summary$cp,xlab="Number of Variables",ylab="Cp")
{% endhighlight %}

In the command above we plotted the `C_p` statistic, which is shown in the image below.  

![plot]({{ base.url }}/images/2016-04-10_001.png)

* Reminder:  `C_p` stands for Mallows `C_p`, which is a way to assess the prediction error of models with different number of predictors. For the definition, go to [wikipedia](https://en.wikipedia.org/wiki/Mallows%27s_Cp).

There is a fancier plot method for the `regsubsets` object, that  will show you exactly which predictors are involved for each resulting value of `C_p`.

{% highlight r %}
plot(regfit.full,scale="Cp")
{% endhighlight %}

![plot]({{ base.url }}/images/2016-04-10_002.png)

