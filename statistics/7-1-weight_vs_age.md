[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

```
from __future__ import print_function

import sys
import numpy as np
import math
import pandas
import first
import thinkplot
import thinkstats2

def ScatterPlot(ages, weights, alpha=1.0):
    """Make a scatter plot and save it.

    ages: sequence of float
    weights: sequence of float
    alpha: float
    """
    thinkplot.Scatter(ages, weights, alpha=alpha)
    thinkplot.Config(xlabel='age (years)',
                     ylabel='weight (lbs)',
                     xlim=[10, 45],
                     ylim=[0, 15],
                     legend=False)
                     

def Corr(xs, ys):
    xs = np.asarray(xs)
    ys = np.asarray(ys)
    meanx, varx = MeanVar(xs)
    meany, vary = MeanVar(ys)
    corr = Cov(xs, ys, meanx, meany) / math.sqrt(varx * vary)
    return corr

def SpearmanCorr(xs, ys):
    xranks = pandas.Series(xs).rank()
    yranks = pandas.Series(ys).rank()
    return Corr(xranks, yranks)

def main(script):
    thinkstats2.RandomSeed(123)
    
    live, firsts, others = first.MakeFrames()
    live = live.dropna(subset=['totalwgt_lb', 'agepreg'])

    ages = live.agepreg
    weights = live.totalwgt_lb
    print('thinkstats2 Corr', thinkstats2.Corr(weights, ages))
    print('thinkstats2 SpearmanCorr', thinkstats2.SpearmanCorr(weights, ages))

    ScatterPlot(ages, weights, alpha=0.1)
    #thinkplot.Save(root='chap07scatter1', legend=False, formats=['jpg'])

if __name__ == '__main__':
    main()

```
