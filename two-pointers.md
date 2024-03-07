# Two Pointers

Two pointers can be used to perform traversal of data structures like arrays and linkedlists in efficient way (usually in O(N) amortized time)







## Traversal over linkedlist

Having a slow pointer and fast pointer on a linked list with different starting positions, and then traverse synchronously.&#x20;

A typical combination of the fast and slow pointers is: that the fast pointer moves **twice** as fast as the slow pointer, such as for cycle detection ([Floyd's Cycle Detection)](graph-theory/cycle-detection.md#floyds-cycle-detection). The idea is to have the fast pointer reach the end of the list first so that the status of the slow pointer becomes meaningful when the length of the list is not given initially.

## Problems

{% embed url="https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/" %}

{% embed url="https://leetcode.com/problems/middle-of-the-linked-list/description/" %}
