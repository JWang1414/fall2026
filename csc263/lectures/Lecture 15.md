Today we begin our study of graph algorithms. The first topic is breadth first search.
# Graphs
We define a *graph* $G=(V, E)$ where $V$ is the set of nodes, and $E$ is the set of edges. $\lvert V \rvert=n$ and $\lvert E \rvert=m$.

An *undirected graph* is one where each edge is an unordered pair suchu that $(u, v)\equiv(v, u)$. A *directed graph* is one where each edge is an ordered pair, so $(u, v)\neq(v, u)$.
- Generally speaking, in directed graphs, the edges are arrows, to indicate the direction. In undirected graphs, they are simply lines

Graphs can, for example, be represented by an adjacency list, which is a list $Adj[1\dots n]$ of $n$ lists, one for each node in $V$. The element $Adj[u]$ is the list of all nodes $v$ such that $(u, v)\in E$.

![[Pasted image 20261104000204.png]]
One example of an undirected graph represented by an adjacency list.
- Note the duplicates. This results because it is undirected

An adjacency matrix is a representation such that:
$$
	A[i, j] = \begin{cases}
	1 & (i, j)\in E \\
	0 & \text{otherwise}
	\end{cases}
$$
- Adjacency matrices of undirected graphs are symmetric about the diagonal
- Adjacency matrices necessarily have size $\Theta(n^{2})$
## When is one preferred?
For sparse graphs $m\ll n^{2}$, the adjacency list is more space-efficient
- Note that the size of the adjacency list is $\Theta(n+m)$ and the matrix is $\Theta(n^{2})$

Determining is edge $(u, v)$ is in $G$ takes $O(1)$ time with a matrix, and $O(n)$ with a list.
# Graph Search
A graph search is done by starting at some node and following its edges to find more and more nodes. This helps to reveal a few things:
- Is $G$ connected?
- Does $G$ have a cycle?
- Information about shortest paths

There are two basic graph searches. *Breadth first search* (BFS), and *depth first search* (DFS).
# Breadth First Search
