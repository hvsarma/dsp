[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
import thinkstats2
import thinkplot
import numpy as np
```

```
t = np.random.uniform(0,1,1000)
pmf = thinkstats2.Pmf(t)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Show()
```

<img src="img/ch04.ex02.png.jpg" title="Uniform random distribution" width="250" style="float: left;" />
