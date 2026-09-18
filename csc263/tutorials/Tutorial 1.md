Our goal is to create a heap from an array $A$ in $O(n)$ time.

Operation: `Max-heapify(A, i)`

Our first building block is to build a function that takes an element $i$ with two left and right subtrees, both max-heaps. Our goal is to turn $i$'s subtree into a heap.

Essentially, imagine we have some max-heap with a root $i$. This procedure is intended to shift $i$ downwards into the heap until the whole thing is a valid max-heap.
- Just the reverse of what happens when we insert something
- Worst-case complexity is $O(h)$ or $O(\log n)$.

Operation: `Build Max Heap(A)`

Begins at $\lfloor n /2 \rfloor$ and iterates to 1. Calling max-heapify on all nodes.
- It works in reverse because of the max-heapify condition. The subtrees must also already be max heaps
- It starts at $\lfloor n /2 \rfloor$ because this is the first non-leaf node

At best, there are $\lfloor n /2 \rfloor$ iterations. So this is $\Omega(n)$

To compute $O$, we require a few more detailed observations:
- A depth $d$ we have $2^{d}$ nodes (in that layer)
- Each node at depth $d$ has height $\leq h-d$
(The height of $x$ is the distance from $x$ to the bottom. The depth of $x$ is the distance from the root to $x$)

So build max heap's cost is at most:
$$
	\sum_{d=0}^{h-1} 2^{d}(h-d) = 2^{h} \sum_{i=1}^{h} \frac{i}{2^{i}}
$$
Where we have defined $i=h-d$.

Recall that $h=\lfloor \log n \rfloor$ and so $2^{h}\leq 2^{\log n}=n$. In the limit where $h\to \infty$ the above becomes:
$$
	n \sum_{i=1}^{\infty} \frac{i}{2^{i}}
$$
From the geometric series we may find the identity:
$$
	\sum_{i=1}^{\infty} ix^{i} = \frac{x}{(1-x)^{2}}
$$
Therefore our series collapses into:
$$
	n \frac{1 /2}{(1-1 /2)^{2}} = 2n
$$
Concluding that build max heap is $O(n)$.

So, it is possible to build a max heap from an array in $\Theta(n)$ time.