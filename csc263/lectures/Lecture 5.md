Recall from last lecture we found that operations on typical BSTs took $\Theta(n)$ time. We would like to limit the height of a BST to $\log n$. Which is achieved with balanced BSTs.
# AVL Trees
Reminder: the height of a node $v$ is the number of edges from $v$ to a leaf. The height of the root node is the height of the tree.
- The height of a single node is 0. And the height of the empty tree is -1.

We define the *balance factor* (BF) of a node $v$ to be the difference between the height of the right and left subtrees of $v$.
- Ideally as close to 0 as possible

An AVL tree $T$ maintains that for every node $v\in T$ has:
$$
	\lvert BF(v) \rvert \leq 1
$$
Balance factors with values 1, 0, and, -1 are called right-heavy, balanced, and left-heavy respectively.

![[Pasted image 20260921194747.png]]
An example of a more complex AVL tree.

![[Pasted image 20260921194808.png]]
An example of an invalid AVL tree.

Important properties of AVL trees to maintain:
- Trees of $n$ nodes have height $\Theta(\log n)$
- Inserts and deletes maintain the tree balance in $\Theta(\log n)$ time

For Insert(T, x), $x$ is inserted into $T$ like normal, and $x$ becomes a leaf. Now, we go through all the nodes which have had their balance factor changed by the addition of $x$, and rebalance if necessary.
- A walkthrough of the general insertion logic is present in the slides

The logic, written out as vague pseudo-code is:
- Insert $x$ into $T$
	- $x$ is now a leaf
- Go up from $x$ to the root. For each node
	- Adjust $BF(v)$
		- If $x$ is in the right subtree, increment $BF(v)$
		- If $x$ is in the left subtree, decrement $BF(v)$
		- If $BF(v)=0$ stop
	- Rebalance if needed
		- If $BF(v)\geq 2$
			- If $BF(\text{Right subtree})=1$
				- Left rotate, update BFs, and stop
			- If $BF(\text{Right subtree})=-1$
				- Right-left rotate, update BFs, and stop
		- If $BF(v)\geq-2$
			- Symmetric to above case
