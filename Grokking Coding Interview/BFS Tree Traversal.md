# BFS Tree Traversal
Useful for level-order tree traversal and various searching. Implemented using a queue to keep track of nodes on a level before jumping to the next level.

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
