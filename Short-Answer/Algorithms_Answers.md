#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) `O(n log n)` - Since the conditional is cubing the value n but we are adding
    the squared value each round to the prior we will never reach `O(n^2)` so we
    fall directly between the bounds of `O(n log n)`.

b) `O(n log n)` - The outer loop is `O(n)` and the inner loop is `O(log n)`.
    Since they must be multiplied to join them, the total is `O(n log n)`.

c) `O(n)` - Although this is a recursive function, its iteration is starting at
    N and decrementing by 1 until it reached 0. That is a negative linear iteration.

## Exercise II

> Devise a strategy to determine the value of f such that the number of **dropped
> \+ broken** eggs is minimized.

### NOTE:
    - The need to account for DROPPED AND BROKEN eggs turns this into a binary
    search.
    - If the output was only concerned with BROKEN eggs, it would be linear search
    up from the 0th floor as the first broken egg would be the only broken egg.
    - If the output was concerned with only the DROPPED eggs and not the broken
    eggs, then it would be a linear search down from the Nth floor as the first
    surviving egg would be the only one that mattered.
---
### PSEUDOCODE: Binary Search: O(log n)
```
SET GOAL:
If the floor being used is the only floor available, it should be the
answer to f. However, if the egg breaks when dropped from this floor, then the
answer to f is the floor directly above.

SET CONTRAINTS:
1. pick the middle floor of the available floors. 

SET CHOICE:
2. drop the egg.
    (a) if broken, try the first step again with floors below
    (b) else, try the first step again with floors above
```