# Min/Max Values

DP is commonly used to solve problems with an answer at the extreme, i.e. min or max values.



In some problems, a value or sum is obtained through more than one property. For example, let's look at the Leetcode problem below:

{% embed url="https://leetcode.com/problems/best-sightseeing-pair/description/" %}

The goal is to maximize the score, which is the sum of two values minus the distance between the two spots. This value score involves multiple properties that will require a high time complexity to compute intuitively.&#x20;

However, the trick here is to usually break the value into properties that can both be maximized/minimized. In this case, we do a little re-grouping:&#x20;

The original score formula: `values[i] + values[j] - (j - i)`

After re-grouping, we have two sub-values: `values[j] - j` + `values[i] + i`.

After the grouping, we can see that the score will be maximized if we can maximize each of these two values.&#x20;

Originally we had to run an O(N^2) to check all possible pairs to find the max score. Now with this, we can only traverse over one fixed endpoint while maintaining the max values for the other end. In other words, we try all possible sub-value 1 while maintaining an optimal sub-value 2 along the way, which becomes an O(N) solution.&#x20;

This works because essentially at any given fixed right endpoint, we only need to know the maximal value on the left, which is only all previous spots we've visited and updated. Since each of the sub-value group can be calculated using the information at one given point, we can update each value conveniently.\


## Similar Questions

{% embed url="https://leetcode.com/problems/maximum-number-of-points-with-cost/description/" %}

