---
layout: post
title: Monte Carlo Simulations in Python - e Estimation!
category: [MonteCarlo, ]
---

## Estimation of e

Here's a simple python function to estimate value of e by sampling from uniform distributions:

```python
num_iters = 1000000

def get_e_trial():
    count = 0
    tot = 0
    while tot <= 1:
        tot += r.random()
        count += 1
    return count

def get_e():
    results = (get_e_trial() for i in range(num_iters))
    return (sum(results) * 1.0) / num_iters

print "e = ", get_e()
```