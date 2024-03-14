# Prefix Sum

## Finding 0 Sum Subarrays

To find subarrays with 0 sum, find prefix sum values of all elements. Then while traversing, if the prefix sum value of any element equals that of another element later, the subarray in between is a 0-sum subarray.  More formally:

For indices `a` and `b` where `a < b`:

If `prefix[b] == prefix[a]`, `sum(a, b, array) = 0` .



{% embed url="https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/description/" %}
