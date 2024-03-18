# Misc

## Overlapping Intervals

Leetcode has a ton of problems about manipulations around intervals, especially merging.

Let's define an interval as $$[a_i, b_i]$$. To detect overlapping intervals, we first sort the intervals based on the starting position. Then, two consecutive intervals intersect if  $$a_2 < b_1$$.

```
|________|
     |________|
```

where the second interval starts before the first one ends.

## Problems

{% embed url="https://leetcode.com/problems/insert-interval/description/" %}

{% embed url="https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/description/" %}
