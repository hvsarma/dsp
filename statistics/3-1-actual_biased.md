[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)
```
from __future__ import print_function
import sys
import nsfg
import first
import pandas as pd 
import numpy as np
import matplotlib
import thinkstats2
import thinkplot
%matplotlib inline
```
```
def ReadFemResp(dct_file='2002FemResp.dct',
                dat_file='2002FemResp.dat.gz',
                nrows=None):
    """Reads the NSFG respondent data.

    dct_file: string file name
    dat_file: string file name

    returns: DataFrame
    """
    dct = thinkstats2.ReadStataDct(dct_file)
    df = dct.ReadFixedWidth(dat_file, compression='gzip', nrows=nrows)
    return df

resp = ReadFemResp()
```

```
pmf = thinkstats2.Pmf(resp.numkdhh)
thinkplot.Pmf(pmf, label='numkdhh')
thinkplot.Show()
```

```
def BiasPmf(pmf, label=''):
    new_pmf = pmf.Copy(label=label)
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
    new_pmf.Normalize()
    return new_pmf
```

```
biased = BiasPmf(pmf, label='biased')

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased])
thinkplot.Show()

pmf.Mean()
biased.Mean()
```
