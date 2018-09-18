[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
x = np.random.random(1000)
pmf = thinkstats2.Pmf(x)

plt.figure(figsize=(12,4))
thinkplot.pmf(pmf, linewidth=.1, color='red')
thinkplot.show(xlabel='Number', ylabel='PMF')
```

![PMF Chart](/Users/brenner/dsp/statistics/output.png)

```python
cdf = thinkstats2.Cdf(x)

plt.figure(figsize=(6,6))
thinkplot.Cdf(cdf, color='green')
thinkplot.Show(xlabel = 'Number', ylabel = 'CDF')
```

![CDF Chart](/Users/brenner/dsp/statistics/output2.png)