# Binomial Heap Operations
Today, we will discuss the implementation of some binomial heap operations. Which were discussed in the last lecture.

First, lets establish some high level ideas.

Two min heap-ordered $B_{k}$ trees can be merged into a single $B_{k+1}$ tree with just one key-comparison
- This arises because of the recursive definition of binomial trees

Deleting the root of a min heap-ordered $B_{k}$ trees results in a min binomial heap.
- Specifically, deleting the root will result in a number of smaller trees. These trees map up the min binomial heap

Roughly speaking, two min binomial heaps can be merged using the following process:
![[Pasted image 20260916152343.png]]
- When two $B_{k}$ trees are added, they form a $B_{k+1}$ tree. Which is carried over
- This form of addition is interestingly identical to the binary addition that is done on the left-side
- A more explicit graphical representation can be seen in the slides. I have not ported then over because it would require too many images
	- The graphical version also makes it clear as to why the number of new edges is equivalent to the number of carries

If $T$ and $Q$ each contain at most $n$ elements, then each of them must also have at most $O(\log n)$ $B_{k}$ trees. Since union requires one key-comparison for each tree, union has time complexity $O(\log n)$

To insert a new value, we will imply piggyback off union. Create a node with one new element, and then merge the node with union. Since the work is done with union, the time complexity is the same. $O(\log n)$

To implement min, which tells us the minimum value, we must scan the roots of the trees, and return the smallest key. There is just $\log n$ trees, so the time complexity is $O(\log n)$.

To extract the minimum value, recall that after we remove the root of a binomial tree, we will get another heap. So, we can just merge them together.

More specifically:
1. Locate the smallest element with Min. $O(\log n)$
2. Delete the root of $B_{i}$ to get another binomial heap. $O(1)$
3. Union the new tree and the trees that were left behind. $O(\log n)$
# Cost of $k$ successive inserts
Say we have a binomial heap $T$ with $n$ elements. What is the cost of $k$ successive inserts?

The time commitment for repeated inserts will be
$$
	O(\log n), O(\log(n+1)), \dots, O(\log(n+k))
$$
This results in a cost $O(k\log(n+k))$
- This seems pretty slow. You need to union every single new element

However, note something interesting. If you repeatedly insert, the cost of insertion will scale with the currently present trees in the heap.
![[Pasted image 20260916154646.png]]
Every single edge corresponds with a key comparison. So there are actually just 8 comparisons, as opposed to the $5\times 5$ we expected. So, the runtime is equivalent to the number of new edges created.

So the total cost here is not actually $O(k\log(n+k))$ comparisons, but it is closer to $2k$ comparisons on average.
# Dictionary
The object has some set $S$ of elements with associated keys.

We would like to: search through the dictionary, insert something new, and remove an entry from the dictionary.

Our first implementation of a dictionary will be done with a binary search tree.
# Binary Search Trees
![[Pasted image 20260916155315.png]]
An example of a binary search tree. Notice that, for each node: keys in the left subtree $\leq$ node's key $\leq$ keys in the right subtree.

In-order traversal is the method of traversal where one first recursively traverses the left subtree, then the node, and then the right subtree. For a BST, in-order traversal visits keys in ascending sorted order. From smallest to largest.
# BST Operations
- Search, Insert, and Delete

To search for a key, simply check if $x$ is smaller or larger than the current node. If it is smaller, go left, larger, go right.
- I will be using $x$ to refer to the value of interest

Insert is much the same. If $x$ is smaller, go left, and larger, go right. Once you eventually reach a leaf of the tree, then $x$ can be added as a new node (to the left or right, if it's smaller or larger).

Delete is slightly more complex.

If a leaf is being deleted, then it can be removed without any hassle.

If a node with one child is being deleted, then the deleted node must be replaced with the child (and its subtree).

If a node with two children is being removed, then we must first find the successor for this node. This can be done by going one step to the right, and going all the way to the left, or vice versa. The successor will always:
- Be the largest value smaller than the node, or the smallest value larger than the node
- Have one child
Now, copy the successor's key into the current node, and delete the successor node. Luckily for this, this problem reduces to one we have already solved before (the successor has at most one child).

In the worst-case, the time complexity of these operations is $\Theta(n)$. This is because the maximum height of a BST with $n$ nodes is $n-1$. However, there are methods to ensure the height is $O(\log n)$.
