---
tags: [interview]
---
# Reversal of Linked list
Doing an in-place reversal of a linked-list is a common problem asked in easier to mid-level interviews (with modification). Without using extra memory, it is difficult to find an efficient solution.

## Example
>Given the head of a Singly LinkedList, reverse the LinkedList. Write a function to return the new head of the reversed LinkedList.

To do this, we have a `previous` pointer and a `current` pointer. The `previous` starts as `NULL` and `current` at the head of the linked list. Every iteration, `next = current->next`,  `current->next = previous`, `previous = current` and then we traverse through the list with `current = next`.

## Problems
### Reverse a Sub-list
We can apply the standard algorithm, taking the previous pointer as start at the start of the sub-list and end the loop when we reach the end of the sub-list. We also need to store the node before the sub-list and the node after the sub-list to link the list after reversing.

### Reverse every $K$-element sub-list
> Given the head of a LinkedList and a number $k$, **reverse every $k$ sized sub-list** starting from the head.

Here, we use a similar algorithm to the previous one, though terminate the loop when we reach $K$ elements reversed. Also be mindful to store the next element after the sub-list to keep track of the entire linked list.