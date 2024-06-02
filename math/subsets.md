---
description: All about subsets
---

# Subsets

## Definition

A **subset** of an array is a selection of elements (possibly none) of the array.

## Generating Subsets

### 1. Recursive Calls

At each element, push one element into the array. Then make a recursive call to the function. After the call, pop out the element and continue to the next decision branch.&#x20;

The logic behind this is that, at every point, there are only two possibilities: either include the element or not. So we make two recursive calls to include all cases.

```cpp
void search(int k) {
    if (k == n) {
        // process subset
    } else {
        search(k+1);
        subset.push_back(k);
        search(k+1);
        subset.pop_back();
    }
}
```

### 2. Bit Manipulation

Use bit representation of the total number of possible subsets to push in corresponding elements into a subset. This can be implemented easily because of the binary decision for whether to put in an element, which matches the property of a binary bit.

```cpp
class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>> ans;
        for(int b = 0; b < (1 << nums.size()); b++){
            vector<int> v;
            for(int i = 0; (1 << i) <= b; i++){
                if(b & (1 << i)){
                    v.push_back(nums[i]);
                }
            }
            ans.push_back(v);

        }
        return ans; 
    }
};

```
