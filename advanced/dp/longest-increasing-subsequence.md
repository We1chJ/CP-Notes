---
description: LIS
---

# Longest Increasing Subsequence

LIS Problem: Find the length of the longest increasing subsequence in an array of elements N

## Approach

{% embed url="https://cp-algorithms.com/sequences/longest_increasing_subsequence.html" %}

Dynamic Programming is suitable for this problem because we can compute the LIS that ends at each element in the array. All we need to compute the next one is to increase the LIS in any previous elements by 1.&#x20;

## Solution 1 $$O(N^2)$$

We define the $$dp$$ array and $$dp[i]$$ as the length of the longest subsequence that ends with the element $$arr[i]$$.&#x20;

Thus: $$dp[i]=max(dp[j] ) + 1$$ for j < i

**Notes**: If we want to restore and find the actual subsequence itself rather than the length, we can just have a separate array storing the index of the second to last LIS we use to compute the current one. Sort of like an ancestor array.&#x20;

We loop through all dp\[j] before i to find the maximum value, which would take $$O(N^2)$$

```cpp
// O(N^2)
int main(){
    cin.tie(0) ->sync_with_stdio(0);
    int n;
    cin >> n;
    vector<int> v ( n);
    for(int i = 0; i < n; i++){
        cin >> v[i];
    }
    vector<int> dp (n, 1);
    for(int i = 0; i < n; i++){
        for(int j = 0; j < i; j++){
            if(v[i] > v[j])
                dp[i] = max(dp[i], dp[j]+1);
        }
    }
    int ans = 0;
    for(auto & a : dp)
        ans = max(ans, a);
    cout << ans << endl;
}
```

## Solution 2 $$O(NlogN)$$

We define a different $$dp$$ array where $$dp[i]$$ stores the smallest last element of a LIS with length `i`

Thus, for every new element `arr[i]`, we need to use it to update the dp array as if we are inserting the new element to a sequence. For every new element, we try to insert it at the longest sequence where the last element is smaller than `arr[i]`.

```cpp
// O(N log N)
int main(){
    cin.tie(0)->sync_with_stdio(0);
    int n;
    cin >> n;
    vector<int> v(n);
    for(int i = 0; i < n ;i++)
        cin >> v[i];


    vector<int> dp(n+1, INT_MAX);
    dp[0] = -INT_MAX;
    
    for(int i =0 ; i < n; i++){
        int pos = upper_bound(dp.begin(), dp.end(), v[i]) - dp.begin();
        if(dp[pos-1] < v[i])
            dp[pos] = min(dp[pos], v[i]);
    }

    int ans =0 ;
    for(int i = 0; i <= n; i++){
        if(dp[i] < INT_MAX)
            ans = i;
    }
    cout << ans << endl;
}
```
