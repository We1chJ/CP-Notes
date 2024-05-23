---
description: All about subsets
---

# Subsets

## Definition

A **subset** of an array is a selection of elements (possibly none) of the array.



## Generate all possible subsets of an array

### 1. Backtracking

At each element, push one element into the array. Then make recursive call to the function. After the call, pop out the element and continue to the next decision branch.

```cpp
class Solution {
public:
    void bt(vector<int> & nums, vector<vector<int>> & res, int i, vector<int> &sub){
        res.push_back(sub);
        for(int a = i; a < nums.size(); a++){
            sub.push_back(nums[a]);
            bt(nums, res, a+1, sub);
            sub.pop_back();
        }
    }

    vector<vector<int>> subsets(vector<int>& nums) {
        vector<vector<int>> res;
        vector<int> sub;
        bt(nums, res, 0, sub);
        return res;
    }
};
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
