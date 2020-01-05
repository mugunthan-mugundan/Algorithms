DFS
	DFS can be done with and without extra memory
	DFS can use a stack or use recursion
BFS
	Requires Queue
Watch out
	Cycles
Interesting algorithms
https://cs.stanford.edu/people/abisee/gs.pdf

The question is when to terminate the traversal
	If you are looking for shortest going BFS may find the solution first.
	Sometimes you have to probe all the paths
		Local minima may not be enough
		https://leetcode.com/problems/campus-bikes-ii/
	Some problems you can work from the local minima
		https://leetcode.com/problems/shortest-path-visiting-all-nodes/
	Some problems require that you remove the edges so you can understand the dependency path
		Topological sort
		https://leetcode.com/problems/alien-dictionary/

Optimization
	Ht of visited nodes
	You can keep the minimal path at each node and use that to build the full path in an HT
Instead of HT you can also use a flag in node to denote visited.

There are different ways of traversing 
	Pre post order etc
	
Storing tree in the disk and rebuilding is also of interest.

Traversals in arrays
	Manhattan distance does not go diagonally
In this case also need to be aware of running out of edges.
