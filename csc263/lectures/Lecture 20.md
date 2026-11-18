Another intuitive formulation of the MST construction theorem.

Suppose there is some MST $T$ of $G$ which contains the spanning forest $T_{1}, \dots, T_{k}$ of $G$. Then, to join the fragments of this forest together, split the forest into one fragment, and the other fragments.

Let $(u, v)$ be an edge of $G$ of minimum weight between the chosen $T_{i}$ and the other trees of the spanning forest. That is $u\in V_{i}$ and $v\in V-V_{i}$. Where $V_{i}$ is the segment of the spanning forest including $T_{i}$.

Then, there is an MST $T^*$ of $G$ that contains $T_{1}, \dots, T_{k}$ and edge $(u, v)$.
# Kruskal's Algorithm
Begin with a list of every edge, sorted from lowest to highest weight. Our current spanning forest is every singleton node. From here, we need to determine what the best choices are.

Well, from the MST theorem, we can connect the first few lowest weight edges, because it is certainly the minimum weight edge between these fragments.

For every minimum weight edge we find, we may join it. However, if we find two nodes $u$ and $v$ in the same set, or fragment, then we reject this edge. This way, we form a minimum weight tree without forming any cycles. Once everything is in the same set, we're done.

![[Pasted image 20261118180104.png]]
The progression of Kruskal's algorithm.

Some undirected graph might have as many as $n^{2}$ edges. However, to create an MST, we just need $n-1$ edges. Since we are sorting every edge, we may have wasted a lot of work.
## Time Complexity
Provided a connected undirected weighted graph $G=(V, E)$ where $V=\{ 1,2,\dots,n \}$ and $E$ is an array of $m$ weighted edges.
```
BuildMinHeap(E)
for i = 1 to n do MakeSet(i)
MST_edges = {}
while |MST_edges| < n-1 do
	(u, v) = Extract_Min(E)
	r = Find(u)
	s = Find(v)
	if r != s then
		Union(r, s)
		MST_edges.append((u, v))
```
- Note that our implementation of Kruskal's algorithm makes use of Min-Heaps and Trees structures. Both of which were introduced previously in this course.

Recall from tutorial BuildMinHeap(E) can be done in $O(m)$ time (since there are $m$ edges). Furthermore, it will trivially take $O(n)$ time to make $n$ singleton sets.

In the worst-case, the while loop will run $m$ times. This is the number of loops required to search through all the edges. First, I will discuss the time complexity of each operation inside of the loop (on its own).

It will take $\log \lvert E \rvert$ time to run Extract_Min(E). However, this is equivalent to:
$$
	\log \lvert E \rvert = \log m < \log n^{2} = 2\log n
$$
Which arises because the number of edges in a graph is limited by the number of vertices such that $n<m<n^{2}$. Each Extract_Min operation within the loop therefore completes in $O(\log n)$ time.

Assuming we are using weighted-union path-compression tree structures, the running time for both Find operations is $O(\log^*n)$.

The segment inside the if-statement only ever be run $n-1$ times. Since it increments the size of MST_edges by 1 every time (and the while-loop ends when MST_edge has $n-1$ elements). Everything inside this if-statement can be done in constant time.

So what is the total time complexity? Well, the while-loop iterates at most $m$ times. So we will at most see $m$ Extract_Min operations, and $2m$ Find operations. These will inflate the time complexity to $O(m\log n)$ and $O(m\log^*n)$, respectively. Combine this with the content inside the if-statement, which will take at most $O(n)$ time in total,
$$
	O(m) + O(n) + O(m\log n) + O(m\log^*n) + O(n)
$$
Which is equivalent to $O(m\log n)$ time.
# Prim's Algorithm
Start from a random node, and extend this node into a bigger and bigger tree. At each step, extend the current tree by selecting the smallest edge out of the tree.