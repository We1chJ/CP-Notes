---
description: I named this category :)
---

# Wormhole Traversal

I've seen a few specific problems from USACO as well as Leetcode that uses this idea.

## Concepts

If we have a 1D array of size `n`, and every element has a **unique** value between `[0,n-1]` (so guarantees no index out of bounds) or similar (sometimes problem context varies), we should be sensitive that a Wormhole Traversal may be used on this array.

Essentially we treat the value of each element of this array as the index of the next element to go to, and turn the array traversal into a linkedlist traversal. This linked list is guaranteed to contain cycles (again, may vary). Any further cycle detections/manipulations can be potentially connected to [floyds-cycle-detection.md](graph-theory/floyds-cycle-detection.md "mention")

## Notes

* This is a very insightful choice especially when numbers are unique in an array, which established the constraints that the `in-degree` and `out-degree` of every element is strictly 1.

## Problems

{% embed url="https://leetcode.com/problems/find-the-duplicate-number/description/" %}

{% embed url="https://leetcode.com/problems/find-all-duplicates-in-an-array/description/" %}
