# DP

DP, dynamic programming, is one of the hardest topic for me at this point. :cry:

The beauty of DP lies not only in its correctness of Brute Force but also in its elegantly efficient approach.&#x20;

## Definition (credits: CPH)

**Dynamic programming** is a technique that combines the correctness of complete search and the efficiency of greedy algorithms. Dynamic programming can be applied if the problem can be divided into overlapping subproblems that can be solved independently.&#x20;

There are two uses for dynamic programming:

* Finding an optimal solution: We want to find a solution that is as **large** as possible or as **small** as possible (min/max problem).&#x20;
* Counting the number of solutions: We want to calculate the **total** number of possible solutions (complete search).

To solve a problem using DP approach, one needs to find a **recursive formula** to derive the states on each sub problems. Then use **memoization** to save them for later use.

Although the idea is somewhat straightforward, but it can be applied in a variety of problems, which makes it one of the hardest topics.&#x20;

(which is why I made this a big chapter and broke it into several sub-pages to finish the content)

## Common Optimizations or Tricks:

1. The dimension of the dp array can be shrunk down when the next value is only dependent on the previous value. Therefore, for example, a 2D array storing all previous answers can be turned into only a 1D array for storing only the previous answers, which will then be updated. In this case, it is also common to traverse the array backward to avoid creating a new copy of the array.
