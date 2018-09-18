[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```python
resp = nsfg.ReadFemResp()
resp['numkdhh'].value_counts()

x = dict(resp['numkdhh'].value_counts())
pmf_all = thinkstats2.Pmf(x)
thinkplot.pmf(pmf_all)

def BiasPmf(pmf):
    new_pmf = pmf.Copy()

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

pmf_kids_3 = BiasPmf(pmf_all)
thinkplot.pmf(pmf_kids_3)

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf_all, pmf_kids_3])
thinkplot.Config(xlabel='Number of kids in HH', ylabel='PMF')

pmf_all.Mean()
#1.024205155043831

pmf_kids_3.Mean()
#2.403679100664282
```

