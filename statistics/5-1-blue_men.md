[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

**Exercise:** In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see [http://bluemancasting.com)](http://bluemancasting.com%29/). What percentage of the U.S. male population is in this range?

```python
import scipy.stats

# Average height is 178 cm (~ 5'11")
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

dist.cdf(185.42) - dist.cdf(177.8)
# Returns 0.3427468376314737
# ~34.3% of men are between the height of 5'11 and 6'1, which would qualify them to join the Blue Man Group.
```


