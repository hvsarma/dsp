[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```
import scipy.stats
%matplotlib inline

def percNormAUC(high, low, mu, sigma):
    dist = scipy.stats.norm(loc=mu, scale=sigma)
    return dist.cdf(high)-dist.cdf(low)
```

```
mu = 178
sigma = 7.7
high_mu_cm = (6*12+1)*2.54
low_mu_cm = (5*12+10)*2.54
percNormAUC(high_mu_cm, low_mu_cm, mu, sigma)
```
