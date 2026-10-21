# Question 3
---
a.
Assuming the index of the first array is one, its children are mapped to $A[3i-1]$, $A[3i]$, and $A[3i+1]$, for each of its children. Their parents are round($A[i /3]$).

A Heapsize variable may be maintained by starting at 1, and incrementing or decrementing everytime a node is inserted or deleted. Alternative, the size of the heap can be determined each time, but I believe this would take $n$ time.

---
b.
The height of a ternary tree is $\lfloor \log_{3}(2n) \rfloor$.
- I got this from stack exchange

Say $h$ is the height of the tree. The number of leaves in the final layer is:
$$
	n-3^{h-1}
$$
- I have no idea how to do this
---
c.
To insert, add the key as a leaf to the heap, and then sort upwards until the heap property is maintained. This is $\Theta(h)$ or $\Theta(\log n)$ time.

To extract max, swap the first node with the last one, and sort the heap until the heap property is maintained. This can be done by swapping the node downwards with the largest node. This can be done in $\Theta(h)$ time.

Navigate to $i$, change its key, and then swap it upwards or downwards until the heap property is maintained. $\Theta(h)$ time.

To remove $i$, swap it with the final node, remove it as a leaf, and then swap the new node to restore the heap property. The logic is the same as the Update operation.