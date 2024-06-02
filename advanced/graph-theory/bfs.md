---
description: Breadth First Search
---

# BFS

The traditional BFS is:





## Order Level Traversal

```
class Solution {
public:
    bool isEvenOddTree(TreeNode* root) {
        queue<TreeNode*> q;
        q.push(root);
        int depth = 0;
        while(q.size()){
            int size = q.size();
            int prev = (depth%2 == 0 ? 0 : INT_MAX);
            while(size--){
                auto node = q.front();
                q.pop();

                if(depth%2 == 0){
                    if(node->val %2 == 0 || node->val <= prev) return false;
                }else{
                    if(node->val%2 == 1 || node->val >= prev) return false;
                }
                prev = node->val;
                if(node->left) q.push(node->left);
                if(node->right) q.push(node->right);
            }
            depth++;
        }
        return true;
    }
};
```





## Problems

[https://leetcode.com/problems/even-odd-tree/description/](https://leetcode.com/problems/even-odd-tree/description/) (BFS level order traversal)
