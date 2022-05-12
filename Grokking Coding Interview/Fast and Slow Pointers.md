# Fast and Slow Pointers
This approach is useful for cyclic linked lists or sequences. As the two pointers move at different speeds, they are bound to meet (i.e finding the middle of a linked list).

## Example
> Given the head of a **Singly LinkedList**, write a function to determine if the LinkedList has a **cycle** in it or not.

We can use a slow pointer which moves by one and a fast pointer which moves by two. If the linked list has a cycle in it, the two pointers will be equal in the traversal of the list. The logic here is that if there is a cycle, the two pointers will eventually converge as they cycle indefinitely. This has an $O(N)$ time complexity.