[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> import numpy as np
sample = np.random.random(1000)
import matplotlib.pyplot as plt
plt.hist(sample, bins = len(sample))
plt.show()

>> def PercentileRank(sample, x):
    count = 0.0
    for value in sample:
        if value <= x:
            count += 1
    
    prob = count / len(sample)
    return prob

percents = []
for val in sample:
    percents.append(PercentileRank(sample, val))

plt.hist(percents, bins = len(percents))
plt.show()
