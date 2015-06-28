[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

```
from __future__ import print_function

import thinkstats2
import thinkplot

import math
import random
import numpy as np

from scipy import stats
from estimation import RMSE, MeanError

def SimulateSample(lamda=2, n=10, m=1000):
    """Sampling distribution of L as an estimator of exponential parameter.

    lamda: parameter of an exponential distribution
    n: sample size
    m: number of iterations
    """
    def VertLine(x, y=1):
        thinkplot.Plot([x, x], [0, y], color='0.8', linewidth=3)

    estimates = []
    for j in range(m):
        xs = np.random.exponential(1.0/lamda, n)
        lamdahat = 1.0 / np.mean(xs)
        estimates.append(lamdahat)

    stderr = RMSE(estimates, lamda)
    print('standard error', stderr)

    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)
    VertLine(ci[0])
    VertLine(ci[1])
    
    #plot the CDF
    thinkplot.Cdf(cdf)
    thinkplot.Save(root='estimation', xlabel='estimate', ylabel='CDF', title='Sampling distribution')
    
    return cdf, stderr

def main():
    thinkstats2.RandomSeed(123)
    print('Simulated n for observing c[i]:')
    for n in [10, 100, 1000]:
        stderr = SimulateSample(n=n)
        print(n, stderr)
        
if __name__ == '__main__':
    main()
