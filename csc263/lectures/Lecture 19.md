Today we introduce the concept of a *minimum spanning tree* (MST).
# Trees
A *tree* is a connected, undirected graph with no cycles.
1. A tree with $n$ nodes has $n-1$ edges
2. Add any edge creates a unique cycle containing that edge. Removing any edge from that cycle results in a tree again.

The *spanning tree* of a an undirected connected graph $G=(V, E)$ is any tree $T$ that connects all the nodes of $G$. We notate this as $T=(V, E')$ where $E'\subseteq E$.
![[Pasted image 20261116221232.png]]
Two examples of spanning trees.
# Minimum Spanning Tree
Let $G=(V, E)$ be a weighted undirected connected graph. This means we add some weight to each of its edges. Then the weight of the spanning tree $T$ is the total weight of its edges.
![[Pasted image 20261116221433.png]]
A weighted undirected connected graph $G$, and the total weights of a few spanning trees.

We call the tree with the minimum-weight the minimum spamming tree of $G$.
# MST Construction Problem
Say we have some weighted undirected connected graph $G=(V, E)$. We would like to create a minimum spanning tree $T$ of $G$.

The first solution one might think of is brute force. Find every single MST, and then compute their weight.
- This is incredibly slow

To solve this problem, we must begin by explaining what a *spanning forest* is.

A spanning forest of $G=(V, E)$ are fragments of a spanning tree of $G$.
![[Pasted image 20261116222339.png]]
An example of a spanning forest.

It is defined to be a set of trees $T_{1}=(V_{1}, E_{1}), T_{2}=(V_{2}, E_{2}), \dots, T_{k}=(V_{k}, E_{k})$ such that $\{ V_{1}, V_{2}, \dots, V_{k} \}$ is a partition of $V$ and $E_{i}\subseteq E$.
## MST Construction Theorem
Suppose some MST $T$ of $G$ contains the spanning forest $T_{1}, \dots, T_{k}$ of $G$.

Let $(u,v)$ be an edge of $G$ of minimum weight between $T_{i}$ and the other trees of the spanning forest $u\in V_{i}$ and $v\in V-V_{i}$.

Then there is an MST $T^*$ of $G$ the contains $T_{1}, \dots, T_{k}$ and edge $(u, v)$
![[Pasted image 20261116223814.png]]
![[Pasted image 20261116223825.png]]
- I don't understand this very well
- I believe it is claiming that if we split $G$ into a spanning forest with $T_{i}$, then split it in half like $V_{i}$ and $V-V_{i}$. The minimum weight edge between these two halves that connects the trees together is a part of the minimum spanning tree.
