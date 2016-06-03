---
layout: post
title: Finding Permutations and Combinations of Lists with Python
---

We often need access to a list of permutations or combinations of a set of numbers. Obtaining those in python is a piece of cake!

Lets say we have a list of numbers [1,2,3] for which we'd like to find all possible permutations and combinations.

```python
import itertools

# itertools.perumatations will return a generator instead of a list
# to obtain a list we simply pass the generator to the list() method

list(itertools.permutations([1,2,3]))
# returns --> [(1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1)]


# What if we want combinations of a list instead of the permutations? 
# itertools provides us with a combinations(iterable, r) method as well
# All in all itertools is awesome!

list(itertools.combinations('ABCD', 2)) 
# returns --> [('A', 'B'), ('A', 'C'), ('A', 'D'), ('B', 'C'), ('B', 'D'), ('C', 'D')]

list(itertools.combinations(range(4), 3))
# returns --> [(0, 1, 2), (0, 1, 3), (0, 2, 3), (1, 2, 3)]

```