# Augmenting Data Structures
Specifically, we are interested in modifying an existing data structure to perform additional operations.
1. What additional info do we need to store for these operations?
2. Can this new info be cheaply maintained?
3. If so, implement it!

Our goal for today is to have a dynamic set $S$ of elements with distinct keys that can: Search(x), Insert(x), Delete(x), Select(k), Rank(x)
- Notice that the first three are already done by a dictionary
- Select(k) finds the $k$th smallest element in $S$. This is called the element with rank $k$
- Rank(x) determines the rank of $x$

For this purpose we will augment the AVL tree.

For our augmentation, we will store the size of the subtree rooted at a node $x$. That is:
$$
	\text{size}(x) = \text{size}(\text{left}(x)) + \text{size}(\text{right}(x)) + 1
$$
So the size of a leaf is 1.

How do we select? We will define the function Select(x, k) where $x$ is some node, and $k$ is the target rank. Let RR(x) be the "relative rank" of $x$. That is the rank of $x$ relative to its own two subtrees.

RR(x) is equivalent to:
$$
	\text{size}(\text{left}(x))+1
$$
There are three cases of interest:
1. $k=RR(x)$ then return $x$
2. $k<RR(x)$ then run Select(left(x), k)
3. $k>RR(x)$ then run Select(right(x), k-RR(x))

Traversing the tree in this manner, we recursively reduce the problem until eventually finding the node with rank $k$. Worst-case complexity is $O(h)$ where $h$ is the height of the tree, or $O(\log n)$.

To implement Rank(x), notice a few things. Lets say we have located $x$ in $T$, and we are now trying to determine the rank of $x$. If we go up one node in the tree to $y$:
1. If $x$ is the right child of $y$ then $RR(x)\leftarrow RR(x)+\text{size}(\text{left}(y))+1$
2. If $x$ is the left child of $y$ then $RR(x)$ is unchanged
![[Pasted image 20260928220222.png]]
An example of how the relative rank changes as we move up the tree

This process may be repeated until reaching the root node, where the rank of $x$ relative to the entire tree has been obtained.

The worst-case time complexity is again $O(h)$ or $O(\log n)$.

Now that we have figured out the new operations. How can we maintain optimal speed for our insert and delete operations?

Well, say we have inserted a new node $x$ into $T$. $x$ is now a leaf with size 1. For each node $y$ on the path from $x$ to the root, increment the size of $y$. Since $x$ has increased the size of these nodes by 1.

Now, once this is done, go and adjust the balance factors, rotating as needed. However, when rotations are done, update the size of the modified trees according to:
$$
	\text{size}(z) = \text{size}(\text{left}(z)) + \text{size}(\text{right}(z)) + 1
$$
- The size of all the non-modified trees are still saved, so this only adds constant work
- I believe the modified trees will be the unbalanced tree, and the first subtree on the unbalanced side.

![[1790647300.png]]
The size and balance factors being modified after a rotation.
