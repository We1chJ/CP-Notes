# Two Pointers

Two pointers can be employed or at least considered, when the movement of each pointer has a **single-direction** (monotonous) effect on some values:

## [Sliding Window](two-pointers.md#sliding-window)

For example, moving the right pointer forward only increases the sum whereas moving the left pointer forward only decreases the sum. Two pointers like this can be used effectively in [Sliding Window ](two-pointers.md#sliding-window)problems. (Famously, [@lee's solutions](https://leetcode.com/problems/binary-subarrays-with-sum/solutions/186683/c-java-python-sliding-window-o-1-space/?envType=daily-question\&envId=2024-03-14))

{% embed url="https://leetcode.com/problems/binary-subarrays-with-sum/description/" %}



Two pointers can be used to perform traversal of data structures like arrays and linkedlists in efficient way (usually in O(N) amortized time)

## Traversal Over Linkedlist

Having a slow pointer and fast pointer on a linked list with different starting positions, and then traverse synchronously.&#x20;

A typical combination of the fast and slow pointers is: that the fast pointer moves **twice** as fast as the slow pointer, such as for cycle detection ([Floyd's Cycle Detection)](../advanced/graph-theory/floyds-cycle-detection.md#floyds-cycle-detection). The idea is to have the fast pointer reach the end of the list first so that the status of the slow pointer becomes meaningful when the length of the list is not given initially.

## Problems

{% embed url="https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/" %}

{% embed url="https://leetcode.com/problems/middle-of-the-linked-list/description/" %}
