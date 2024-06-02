# Binary Search

Binary Search can usually be used to find an optimal solution/value, if the results are **monotonous** (i.e. one-directional):

* Boolean: `TTTTTTTTTTTTTTFFFFFFFFFFFFFFFF`
* Numbers: `[1, 2, 3, 5, 6, 88, 999]`

The data needs to be sorted in a one-directional order, such that every time we are testing for a `mid` point, we can always eliminate half of the data, resulting in an extremely efficient solution.

## Template

Note: The formula for `mid` , the while loop condition, and updating `l` and `r` can vary slightly depending on the problem context.

```cpp
int l = 0, r = n;
while(l < r){
    int mid = (l+r+1)/2;
    if(function(mid))
        l = mid;
    else
        r = mid-1;
}
return l;
```

## Trials and Errors

This is a common way to employ Binary Search to efficiently find a desired optimal value (min/max) under a specific problem context. The method is to try possible values one by one and test if it satisfies the conditions

If we notice that:

1. The outcome of each trial is in monotonous order.
2. There are obvious easy/efficient ways to test a number in the problem. (e.g. O(N) time complexity)

Binary Search will likely be an ideal solution.
