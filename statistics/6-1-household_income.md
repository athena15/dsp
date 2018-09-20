[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

**Importing modules, loading up the data set, and setting an upper bound on the sample.**

```python
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import brfss

import thinkstats2
import thinkplot

def InterpolateSample(df, log_upper=6.0):
    """Makes a sample of log10 household income.

Assumes that log10 income is uniform in each range.

df: DataFrame with columns income and freq
log_upper: log10 of the assumed upper bound for the highest range

returns: NumPy array of log10 household income
"""
# compute the log10 of the upper bound for each range
df['log_upper'] = np.log10(df.income)

# get the lower bounds by shifting the upper bound and filling in
# the first element
df['log_lower'] = df.log_upper.shift(1)
df.loc[0, 'log_lower'] = 3.0

# plug in a value for the unknown upper bound of the highest range
df.loc[41, 'log_upper'] = log_upper

# use the freq column to generate the right number of values in
# each range
arrays = []
for _, row in df.iterrows():
    vals = np.linspace(row.log_lower, row.log_upper, row.freq)
    arrays.append(vals)

# collect the arrays into a single sample
log_sample = np.concatenate(arrays)
return log_sample

# Load the sample into dataframe
sample = np.power(10, log_sample)
```
**Compute the median, mean, skewness and Pearson's skewness of the resulting sample.**

```Python
median = np.median(sample)
# 51226.93306562372

mean = np.mean(sample)
# 74278.7075311872

std = np.std(sample)
# 93946.92996347835

scipy.stats.skew(sample)
# 4.949920244429584

def pearson_median_skewness(mean, median, std):
    return 3 * (mean - median) / std

pearson_median_skewness(mean, median, std)
# 0.7361105192428792
```

**What fraction of households reports a taxable income below the mean?**

```python
cdf2.Prob(mean)
# 0.660005879566872
# 66.0% of households report a taxable income below the mean.
```

**How do the results depend on the assumed upper bound?**

Removing the upper bound of $1,000,000 would increase the mean and cause the overall distribution to be even more positively skewed. With the mean going up, the percentage of households that make less than the mean is only bound to go up as well.