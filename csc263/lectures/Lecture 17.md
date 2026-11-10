Today we introduce depth first search (DFS).

In BFS, the first discovered is the first explored. In DFS, the last discovered is the first explored. Just like in BFS, DFS keeps track of:
- $\text{color}[v]$, the colour of $v$
- $p[v]$, which is $u$ if $u$ discovered $v$

But DFS will also track:
- $d[v]$ the time $v$ is discovered
- $f[v]$ the time $v$'s exploration is completed

To track the time, DFS uses a counter that is incremented by 1 whenever a new node is discovered, or whenever it finishes exploring a node.

- One way to visualize how DFS traverses trees is by travelling all the way down a single branch, and then clearing out everything at the end before moving back up to the original node
- The worse-case time complexity of DFS is $O(\lvert V \rvert+\lvert E \rvert)=O(n+m)$

By tracking which node is the first to discover another, we can use those connections to form a DFS forest.
![[Pasted image 20261109211719.png]]
A DFS forest is highlighted by the solid lines.
# Edge Classification by DFS
A DFS of a directed graph $G=(V, E)$, with edges $(u, v)\in E$, classifies the edges of $G$ as follows:
- *Tree edge* $\iff u$ is the parent of $v$ in the DFS forest

- *Forward edge* $\iff u$ is an ancestor of $v$ in the DFS forest
- *Back edge* $\iff u$ is descendent of $v$ in the DFS forest
- *Cross edge* $\iff u$ is neither an ancestor or descendent of $v\iff$ not a forward or back edge

Note that the last three classifications apply only if the edge $(u, v)$ is not a tree edge.
# DFS Properties
$u$ is an ancestor of $v\iff d[u]<d[v]<f[v]<f[u]$
- The exploration of $v$ must complete within the exploration of $u$

For any two nodes $u$ and $v$, we cannot have $d[u]<d[v]<f[u]<f[v]$
- Expansion on the above property

If $(u, v)\in E$ then $d[v]<f[u]$
- So for some edge $(u, v)$, the node $v$ must surely be discovered before we finish exploring $u$

Now, the classification of the edges can be expanded upon with these properties.

In a DFS of a directed graph $G=(V, E)$, each edge $(u, v)\in E$ is either:
- Tree or forward edge $\iff d[u]<d[v]<f[v]<f[u]$
	- $v$ is a descendent of $u$
- Back edge $\iff d[v]<d[u]<f[u]<f[v]$
	- $u$ is a descendent of $v$
- Cross edge $\iff d[v]<f[v]<d[u]<f[u]$

![[Pasted image 20261109220536.png]]
An example of a graph $G$ that has been traversed with DFS. The solid lines are tree edges. Forward, back, and cross edges are notated with F, B, and C, respectively.
- I believe each node may only have one tree edge pointing towards them. Which is why some of the forward edges are not also tree edges. It just depends on which edge is traversed first.

- There are a number of examples in the slides going through the classifications, and DFS traversal. I will not include them here