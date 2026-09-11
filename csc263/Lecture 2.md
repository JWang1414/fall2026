During this lecture we will be discussing max heaps. But, first we will define a few things.

An *abstract data type* describes an object and its operations, but a *data structure* is the specific implementation of an ADT.
- So one is the description, and one is the actual implementation

An example of an ADT might be a priority queue. Which contains some set of elements, each with a key or priority. It can...
- Insert $x$ into $S$. Return the highest priority in $S$. And pop out the highest priority in $S$

This can be applied, for example, in an OS where a priority queue decides the set of jobs to schedule.

![[Pasted image 20260911151913.png]]
A few examples of simple priority queue implementations, and the associated efficiency.
# Visualizing Max-Heaps
Elements in max-heaps are stored in a *complete binary tree*. That is:
- It is a binary tree
- Every level $l$, except for maybe the bottom, has $2^{l}$ nodes
- All nodes in the bottom are pushed to the left side

![[Pasted image 20260911152150.png]]
An example of a complete binary tree.

The *height* of a tree is the number of *edges* in the longest path from the root to any leaf. In the above example, the height is 3.
- Some people will defined it as the number of vertices. So this tree has height 4 in this case. We don't do this though

Now, it is easy to prove that the height of a complete binary tree is $n$ nodes is $\lfloor \log n \rfloor$
- Logarithms have base 2 here

Inside of a max-heap, the priority of each node must be greater or equal to the priority of its children
- Note that the max-heap of $S$ is not unique. You can swap around numbers

To represent this max-heap inside as an array, we will simply fill it in starting from the root, and then go down the levels.

![[Pasted image 20260911153016.png]]
The array representation of a max-heap.

This representation guarantees that the left child of $A[i]$ is at $A[2i]$ and the right child at $A[2i+1]$. The parent is located at $A[\lfloor i /2 \rfloor]$.
# Implementing Operations
To insert, we will begin by adding our new value at the end. Now, if the parent node is smaller than the new node, swap the two. Repeat this until we find a suitable location for the new node.
- Operation is $\Theta(\log n)$

Printing the max value has $\Theta(1)$. Since we just need to print the root value.

To extract the max value, we will remove the root, and place the last value in the array up there. Now, we can simply swap downwards (with the larger child) until the max-heap conditions are fulfilled.
- Operation is $\Theta(\log n)$

One application of a max-heap might be HeapSort. Simply make a heap out of your elements $(\Theta(n))$ before extracting the max value $n$ times. Which results in a sorting time of $\Theta(n\log n)$.
- Can be done in-place
