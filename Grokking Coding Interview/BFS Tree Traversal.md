# BFS Tree Traversal
Useful for level-order tree traversal and various searching. Implemented using a queue to keep track of nodes on a level before jumping to the next level. Also guaranteed to find the target node unlike DFS, which may get stuck in a loop.

Psudeocode of BFS:
```
BFS(G, root):
	let Q be a queue
	label root as explored
	enqueue root onto Q

	while Q is not empty:
		curr = Q.pop()
		for curr neighbours "n":
			if n not explored:
				label n as explored
				enqueue n onto Q
```

## Problems
### Level-Order Traversal
Run a BFS, and to keep track of the levels use a 2D array. Every time we enqueue a node, add the node to an array. After we add all the nodes (i.e after the `for` loop), move the array into the larger 2D array to keep track of the level.

### Reverse Level Order
Same as previous, just populate the array in reverse order.

### Zigzag Traversal
Run a BFS and keep track of the levels as before. Though, when the current size of the complete list of levels is even, reverse the current level list and append it.

### Level Averages
Run a BFS and keep track of the levels as before, though calculate their average and append it to the main list.

### Minimum Depth
Use a BFS, and for the first leaf-node, return its depth. We can keep track of depth by incrementing it at the start of every iteration.

### Level Order Successor
Use a BFS and once we find the target node, return the next node popped off of the queue.

### Connect Level Order Siblings
> Given a binary tree, connect each node with its level order successor. The last node of each level should point to a `null` node.

Define a current node and use a BFS. The current node should represent a node in the linked list. Link the `next` field of the current node to the next node popped in the queue, and set current to the node popped.