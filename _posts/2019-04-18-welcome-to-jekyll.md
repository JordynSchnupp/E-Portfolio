---
title: "Euler Problem 48 (Python)!"
date: 2023-11-11T15:34:30-04:00
categories:
  - blog
tags:
  - Python
  - Codes
  - Euler Problem
---

I am focusing on Problem 48 "Self Powers" from [ProjectEuler.net][https://projecteuler.net/problem=48]:

The problem:
The series, 1^1 + 2^2 + 3^3 + … + 10^10 = 10405071317.
Find the last ten digits of the series, 1^1 + 2^2 + 3^3 + … + 1000^1000.

Jupyter Notebook:

Here is the raw code not in a Jupyter Notebook:

```ruby
#Project Euler Problem #48 - Self Powers

L = 1000    
d = 10**10
#s = sum(pow(n, n, d) for n in range(1, L+1)) 
s = sum(pow(n, n) for n in range(1, L+1)) 

print "Solution = %d" % (s % d)
#=> Prints "Solution = 9110846700"
```

This was an interesting problem for me to solve because of how large the solution can be if you do not take the sum of the 10 least significant digits. I found that I did not need to use the modpow implementation in my program by using Python's pow function. Though for some fun, I went ahead and also used the modpow function to solve this problem as well. 

```ruby
#Project Euler Problem #48 - Self Powers

def modpow(z, a, m):
  n = 1
  while a > 0:
    if a & 1:
      n = (n * z) % m
    z = (z * z) % m
    a = a >> 1
  return n

#=> Solves to: 9110846700
```