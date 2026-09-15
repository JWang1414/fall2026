Last lecture we completed one possible implementation of the priority queue abstract data type.

Recall that it had the operations Insert, Max, and Extract_Max.

We would now like to implement a Union operation to merge to priority queues into one. We'll call this a "mergeable priority queue"

This will be done using a *binomial heap*.
# Visualizing Binomial Heaps
Elements are stored in a sequence of binomial trees.

These trees are constructed such that $B_{0}$ is a single node, $B_{1}$ is a connection between two single nodes, and so on. They are defined so that $B_{k}$ is made out of two $B_{k-1}$ trees.

![[Pasted image 20260914192228.png]]
An example of a $B_{4}$ level binary tree. Highlighting how it is made out of several smaller binary trees.

The depth of a binary tree is defined as the number of edges from the root node. The root node has depth 0, and the lowest node here has depth 4.

Note that the number of nodes at each depth is equivalent to $\begin{pmatrix}\text{Height} \\  \text{Depth}\end{pmatrix}$.

We conclude that $B_{k}$ tree has height $k$, $2^{k}$ nodes, and $\begin{pmatrix}k \\  d\end{pmatrix}$ nodes at depth $d$.

A *binomial forest* $F_{n}$ of size $n$ is a sequence of $B_{k}$ trees with strictly decreasing $k$'s and a total of $n$ nodes.

To determine which binary trees to use to construct a binary forest, convert the number of nodes $n$ to binary.

![[Pasted image 20260914193822.png]]
An example of a binary forest with $n=9$

Notice that the trees in a binary forest are exclusively the ones in the binary representation of $n$.
- Note that the largest bit will always be $\lfloor \log_{2} n \rfloor$

Let $\alpha(n)$ be the number of 1's in the binary representation of $n$. Then $F_{n}$ has $\alpha(n)$ trees, and $n-\alpha(n)$ edges.

A *min binomial heap* of $n$ elements is a binomial forest $F_{n}$ such that
1. Each node stores one element
2. Each $B_{k}$ tree is min-heap ordered. That is, it satisfies the min-heap properties defined last lecture
	- Note the wording. Each tree, not the entire forest. Each individual tree must satisfy the conditions, but the values in $B_{0}$ need not be smaller than all values in $B_{1}$, for example.

- To build binomial heap, there must one key-comparison per edge. So a binomieal heap with $n$ elements can be built in $O(n)$ comparisons
# Storing Binomial Heaps in Memory
![[Pasted image 20260914211718.png]]
The nodes of binomial heaps are connected to each other using the following pointers.
# Binomial Heap Operations
The union operation is challenging to visualize without the slides. However, the general idea is that you can determine the new trees in the forest simply by adding the number of nodes in your two binary heaps, and checking its representation in binary.

The merging process is a little more complex. A comparison is made between each root node, and the trees are progressively merged together (remember the trees are recursive) until it matches the trees determined earlier.

If the two trees $T$ and $Q$ contain at most $n$ elements
$$
	\lvert T \rvert \leq n \qquad \lvert Q \rvert \leq n
$$
Then each of them will have at most $O(\log n)$ $B_{k}$ trees. A union operation requires checking each of the trees in $T$ and $Q$ with each other at least once. Therefore, it will take at most $O(\log n)$ key-comparisons.
