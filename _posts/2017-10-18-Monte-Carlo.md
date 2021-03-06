---
layout: post
title: Monte Carlo Estimation of Pi
category: ['Python One Liners', 'Monte Carlo']
---

This blogpost provides a way to calculate the approximate value of pi using the Monte Carlo method.

<p style="text-align: center;">
<img src="/images/inscribed_circle.jpg" align="center">
</p>


The fraction of area of circle by the area of square multiplied by four gives the value of 'π'.

A simple way to compute this fraction is to generate the points in the square and count the number of points which lie in the inside of the circle.

<p style="text-align: center;">
<img src="/images/generate_points_pi.jpg" align="center">
</p>

The approximation of the 'π' is

<p style="text-align: center;">
<img src="/images/approximation_pi.jpg" align="center">
</p>

## Monte Carlo method for Pi
The Monte Carlo method uses the previous idea to compute the value of 'π'. The method randomly generates points in the square '[-1, 1] x [-1, 1]' and counts the number of points in the inside of the unit circle. The result is four times the fraction between the number of points which lie in the inside of the circle and the number of all generated points.

Here's a simple python function to estimate value of pi by sampling from uniform distributions:

```python
import random as r
num_iters = 1000000

def get_pi():
    results = ( (r.random()**2 + r.random()**2)**0.5 < 1 for i in range(num_iters) )
    return (sum(results) * 4.0) / num_iters

print "Pi = ", get_pi()
```
