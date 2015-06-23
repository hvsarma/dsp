[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d): Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s d to quantify the difference between the groups. How does it compare to the difference in pregnancy length? 

Cohen's d is defined as the difference between two means divided by a standard deviation for the data, i.e. 

d = (group1.mean - group2.mean) / pooled_sample_variance. 

1) Initialize and import modules

```
import nsfg
import math
```

2) Load the dataset in to a python Data Frame

`df = nsfg.ReadFemPreg()`

3) Extract data subsets (first babies vs. others), using `birthord` variable in the dataset.

```
firsts = df[df.birthord==1]
others = df[df.birthord>1]
n1 = len(firsts)
n2 = len(others)
print n1, ',', n2
```

4) Sample size:

Number of first babies in the sample = 4,413; and number of other babies = 4,735.

5) Sample Statistics

5a) Calculate the mean weights of the two groups.
```
print firsts.totalwgt_lb.mean()
print others.totalwgt_lb.mean()
```

Mean weight (lbs) of first babies = `7.20109443044`. Mean weight of other babies = `7.32585561497`

Data above shows that first babies are slightly lighter in weight (lb), based on the sample available. The (alternative) hypothesis is that, first babies are lighter than others. (Null hypothesis is that there is no significant difference in mean weights of two groups)

5b) Difference in weights in lbs (= `-0.124761184535`) is quite small to see the effect.

```
diff = firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
print diff
```

5c) Sample variances and pooled variance
```
var1 = firsts.totalwgt_lb.var()
var2 = others.totalwgt_lb.var()
pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
```

5d) Cohen's d estimate
```
d = diff / math.sqrt(pooled_var)
print 'Cohen\'s d estimate is' , d
```

6) Result:

Cohen's d estimate is `-0.0886729270726`.

Comparing this estimate with the standard normal distribution, Z-statistic for alpha=0.05 (-1.96),  there is no significant evidence to believe that the mean weight difference of -0.12lbs is big enough to say first babies are lighter.
