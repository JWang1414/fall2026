Many problems are NP-complete, and so are unlikely to have polynomial time algorithms.

To attempt to solve these, one idea that comes to mind is solving them approximately as opposed to exactly.
# Traveling Salesman Problem
Recall from the previous lecture we found that we can find an MST of a graph $G$ in $O(m\log n)$ time with Kruskal's algorithm.

In this problem we are provided an undirected complete graph $G=(V, E)$ with non-negative edge weights/costs. We would like to find a tour of $G$ with minimum total cost.
- A tour is a cycle that visits every node of $G$ exactly once

It is possible to brute force this problem, but it would take exponential time. Furthermore, the TSP is NP-hard.

One method of simplifying this problem is assuming the edge costs all satisfy the triangle inequality, which we will call $\Delta$ inequality. This essentially states that for three nodes $u$, $v$, $w$ in $G$:
$$
	c(u, v) \leq c(u, w) + c(w, v)
$$
So it always costs less to go directly from $u$ to $v$, instead of taking a stopover at $w$.

This simplified version of the problem is called $\Delta$-TSP, or metric TSP.

Unfortunately $\Delta$-TSP is still NP-hard, however, an approximate solution can be determined in polynomial time.
- This algorithm finds a tour of $G$ whose cost is within a fixed constant factor of the optimal tour
## Cost of TSP vs. cost of MST
Lemma: Let TSP be an optimal tour of $G$. Let MST be a minimum spanning tree of $G$. Then $\text{cost}(MST)\leq\text{cost}(TSP)$.

Consider any TSP of $G$. If you remove one edge you get a spanning tree of $G$. Trivially, $\text{cost}(ST)\leq\text{cost}(TSP)$, since one edge is removed. Since $\text{cost}(MST)\leq\text{cost}(ST)$ by definition, we must also have:
$$
	\text{cost}(MST) \leq  \text{cost}(TSP)
$$
As needed.
## Approximation for $\Delta$-TSP
Say we have a complete graph $G$ with edge weights that satisfy the $\Delta$-inequality.
1. Find an MST of $G$
2. Do a full walk of the MST
3. Transform the cycle into a tour by removing repeated nodes

It will take $O(m\log n)$ time to find an MST of $G$. As discussed prior with Kruskal's algorithm.

A full walk entails travelling to each node in $G$ along the MST. This essentially means we traverse each edge of the MST twice. This full walk essentially gives us some cycle $C$ which goes through every node in $G$, but has several duplicates.
![[Pasted image 20261124144557.png]]
A full walk looks something like this.

Now we have a cycle of $G$ (not a tour) with $\text{cost}(C)=2\text{cost}(MST)\leq2\text{cost}(TSP)$. The final step is to transform this into a tour $C^*$ by removing the repeated nodes. Which, by the $\Delta$-inequality, $\text{cost}(C^*)\leq\text{cost}(C)$.

![[Pasted image 20261124145016.png]]
The tour $C^*$ we obtain after removing the repeated nodes from $C$.

The final cost of the cycle is:
$$
	\text{cost}(C^*) \leq 2\text{cost}(MST)
$$
So the cost of $C^*$ is at most twice the cost of the TSP tour.
## Modern times
Generally speaking, the best approximation somebody has found for this problem is bounded by $1.5\text{cost}(TSP)$. Which is a lot better than what we found. It is possible to find one within $(1.5-\epsilon)\text{cost}(TSP)$, however this algorithm is so much more complex it is hardly worth considering in any practical sense
- Note that $\epsilon$ is some constant $\epsilon>10^{-36}$

Unless $P=NP$ no polynomial-time algorithm can guarantee a ratio below 123/122. So there's still quite a large gap to cover.
