Today we discuss and analyze disjoint sets. Recall that a disjoint set is a collection $S_{1}, \dots, S_{k}$ of sets. Each set is identified by some representative element in it.

Assuming no duplicate elements, we are interested in implementing a Find and Union operations. Which are responsible for finding the representative of $x$'s set, and merging two sets represented by $x$ and $y$.

In the CLRS textbook, Union instead merges the sets containing $x$ and $y$. Which is simply Union(Find(x), Find(y)) in our notation.

Furthermore, in CLRS they create a MakeSet(v) operation, which creates a singleton set $\{ v \}$. We just assumed everything was already a set.
# Graphs
A *graph* is a set of nodes with edges between them. *Connected components* are two components that can "reach other" with the edges.

Now, given $v_{1}$ and $v_{2}$ as a query, determine if they are in the same component.
- Lets solve this problem using disjoint sets.

First, create a collection of disjoint sets that represent these graphs:

ConnectedComp(G)
```
for each edge (u, v) in G:
	ru = Find(u)
	rv = Find(v)
	if ru != rv:
		Union(ru, rv)
```

And to determine if they are in the same graph:

SameComp(G, a, b)
```
if Find(a) == Find(b):
	return True
else
	return False
```


Alternatively, we might try to solve this problem using linked lists. Each element is a node in the list, and the representative is the first node. Furthermore, each node will have a pointer to the next node, and a pointer to the representative. The second node is to speed up Find operations.

To implement Find(x), we just return $x$'s representative pointer. For Union, however, we must update the representative pointers of the new list after appending the two.
- To speed up Unions, we will always append the shorter list to the longer list.

For some sequence of Unions and Finds, where $n$ is the number of elements, and $m$ is the number of Finds, what is the runtime? We would like to show that, with a linked list, and the weighted-union heuristic, the runtime is $O(m+n\log n)$.

Trivially, it will take $O(m)$ time to complete $m$ Finds.

To approach the runtime of the Union operations, we first ask: How many times is a particular $x$'s rep. pointer updated?

Well, in each update, $x$ must have been in the smaller list, and so the size of $x$'s list at least doubles. After $k$ updates, $x$'s list has $2^{k}$ elements. Now, there are just $n$ elements, and so $x$'s list can have at most $n$ elements.
$$
	2^k \leq  n \implies k\leq  \log n
$$
So the total update cost is $\log n$. For all $n$ elements, this is $O(n\log n)$ time.

The total runtime is therefore:
$$
	O(m+n\log n)
$$
