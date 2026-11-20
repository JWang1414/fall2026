We will be going over minimum spanning trees this tutorial. Discussing another algorithm for forming an MST, different from Kruskal's.

MST uniqueness theorem:
> If a graph $G$ has distinct edge weights, it must have a unique MST.

Suppose for contradiction that $G$ has two distinct MSTs $A$ and $B$.

Now, imagine the set of edges in $A$ and $B$. Since $A$ and $B$ are two distinct sets, there are some edges that are in just one of them. Notate this difference between the two as $\text{diff}(A, B)$.

Let $e_{1}$ be the edge of smallest weight in $\text{diff}(A, B)$. We may assume that $e_{1}\in A$ and $e_{1}\not\in B$ without loss of generality.

Add $e_{1}$ to $B$ to create the new tree $B'$. $B'$ will now have a cycle $C$ that contains $e_{1}$. Since $A$ cannot contain $C$, there must be some edge $e_{2}\in C$ such that $e_{2}\not\in A$.

Notice that $e_{2}\neq e_{1}\implies e_{2}\in B\implies e_{2}\in\text{diff}(A, B)$. Furthermore, by definition, $e_{2}$ is heavier than $e_{1}$.

Define a new tree $B^*$ which is $B'$ with $e_{2}$ removed. This breaks the cycle $C$, resulting in another spanning tree. However, $B^*$ must necessarily be a lighter spanning tree than $B$. QED
# Prim's Algorithm
Begin from one node in $G$, and grow edges one by one to construct a minimum spanning tree.