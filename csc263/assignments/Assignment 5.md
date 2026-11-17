# Question 1
---
a.
I will assign a charge $2\alpha$ to each Add operation, and 0 to each Reduce operation.

---
b.
To prove a credit invariant, I require:
1. Each element in $S$ must have $2\alpha$
2. Total charge $\geq$ total cost

Proof by Induction.

Define a sequence of operations (Add or Reduce) $\sigma$ of length $k$.

Base case: $k=0$

There are no operations. The current size of $S$, $n$, is 0. Every element therefore has $2\alpha$. The total charge is 0, and the total cost is 0. So total charge $\geq$ total cost.

Inductive step: Assume the credit invariant holds after $k$ operations. I want to show that it holds after $k+1$ operations.

Case 1: Add

A new element $x$ is appended to the beginning of $S$. $x$ is charged $2\alpha$, maintaining (1). Furthermore, the total cost of Add is 0, so the total charge is trivially greater.

Case 2: Reduce

$\lceil n /2 \rceil$ elements are removed from $S$, which originally has $n$ elements. Note that the total cost of Reduce is $\alpha n$. The charge that is saved up in the removed elements is:
$$
	2\alpha \left\lceil  \frac{n}{2}  \right\rceil \geq  \frac{2\alpha n}{2} = \alpha n
$$
So, the credit built up in the removed $\lceil n /2 \rceil$ elements can pay for the Reduce operation. (2) is maintained.

Furthermore, note that the credit in the remaining $\lfloor n /2 \rfloor$ element is untouched, and therefore they maintain $2\alpha$ each. (1) is maintained.

---
c.
For $k$ operations, the amortized cost is therefore:
$$
	\frac{2\alpha k}{k} = 2\alpha \in O(1)
$$
# Question 2
---
a.
1. $\Theta(\log n)$, for $S$ of size $n$. Binary search cuts the array in half each step. The total number of cuts is at most order $\log n$
2. $\Theta(n)$, for $S$ of size $n$. $x$ must be inserted into the array, and at most $n$ elements must be shifted one over to accommodate the new element

Compute the worst case time for $n$ insertions.
$$
	\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$$
The amortized insertion time is therefore:
$$
	\frac{1}{n} \frac{n(n+1)}{2} = \frac{n+1}{2} \in \Theta(n)
$$
---
b.
The first instance:
$$
	\{ [4], [2, 6, 7, 11] \}
$$
The second instance:
$$
	\{ [16], [2, 7], [0, 5, 9, 11] \}
$$
---
c.
Use binary search to search through each sorted array $A_{i}$ one by one. The worst-case runtime will be:
$$
	\sum_{i=0}^{k-1} b_{i} \log(2^{i}) = \sum_{i=0}^{k-1} ib_{i}
$$
Notice that the runtime for each array $A_{i}$ is $\log(2^{i})$. In the worst-case scenario, all $b_{i}=1$.
$$
	= \sum_{i=0}^{k-1} i = \frac{k(k-1)}{2} \in O(k^{2})
$$
The worst-case time complexity is therefore $O(\log ^{2}n)$
- I don't think I need these calculations here. Might be over-complicating this question

---
d.
If $b_{0}=0$, then $A_{0}$ is empty, and $x$ may be inserted into $A_{0}$. Otherwise, $x$ must be Merged (as in MergeSort) with the currently existing element in $A_{0}$. Once this is complete, Merge the modified $A_{0}$ with $A_{1}$. Repeat this sequence of Merging $A_{i}$ with $A_{i+1}$ until $b_{i+2}=0$. That is, until there is no $A_{i+2}$ to chain Merges into.

Assume each Merge operation completes in $O(n)$ time, where $n$ is the length of the arrays being merged together. The worst-case runtime is:
$$
	\sum_{i=0}^{k-1} b_{i} 2^{i} = \sum_{i=0}^{k-1} 2^{i} = 2^{k}-1 \in O(2^{k})
$$
Notice the runtime of each Merge operation is $2^{i}$. Using the fact that $k=O(\log n)$, the worst-case time complexity is $O(n)$.

---
e.

# Question 3
---
a.
## Explanation
Example of an adjacency matrix with $n=6$ nodes. 5 is the leader node. Notice that all elements $(i, i)=0$, since there are no self loops.
$$
	\begin{bmatrix}
	0 & 1 & 0 & 1 & 1 & 0 \\
	1 & 0 & 0 & 0 & 1 & 0 \\
	0 & 0 & 0 & 0 & 1 & 1 \\
	0 & 1 & 0 & 0 & 1 & 0 \\
	0 & 0 & 0 & 0 & 0 & 0 \\
	0 & 0 & 0 & 0 & 1 & 0
	\end{bmatrix}
$$
Some facts about leader nodes. Which I will denote as $l$:
1. All values along the row $l$ are 0
2. All values along the column $l$ are 1. Except for $(l, l)$

What follows from facts 1 and 2 is the following observation: If a non-leader node has a row of all '0's, or a column of all '1's, then there cannot be a leader node. This is simply because the existence of a leader node would render such a non-leader node impossible.
- Not sure if this line is needed anymore

To search for the leader node, I will maintain a direct access array of "leader candidates" $LC$ of size $\lvert V \rvert$. For some index $1\leq i\leq \lvert V \rvert$, $LC[i]=1$ indicates that node $i$ might be a leader node, and $LC[i]=0$ indicates that node $i$ cannot be a leader node.

I begin by reading the first row, skipping over elements on the diagonal, because they must be 0. If element $i$ on the first row is 1, then $LC[i]=1$. Otherwise, $LC[i]=0$. Furthermore, if there is a 1 found on the first row, $LC[1]=0$. Repeat this process on row 2, 3, and so on, until reaching the end of the adjacency matrix.

If there is a candidate left, then this is the leader. Otherwise, there is no leader.

For example, after reading the first row in my example, the candidates would be 2, 4, and 5. Or $LC=[0, 1, 0, 1, 1, 0]$. In the following row, it is limited to just $LC=[0, 0, 0, 0, 1, 0]$. This remains the case until the algorithm terminates, and declares node 5 is the leader node.
## Pseudo-code
```
LC = [1] * |V|

# Find the leader node
for row = 1...|V|:
	for col = 1...|V|:
		# Skip diagonals
		if row = col: continue
		
		# Update leader candidates
		current = A[row, col]
		LC[col] = LC[col] and current
		LC[row] = LC[row] and !current

# Print the results
for i = 1...|V|:
	if LC[i]:
		print(i)
print("G has no leader node")
```
## Proof
- Do this later
---
b.
In the worst-case, my algorithm will read through every element in $A$ one time, excluding the elements along the diagonal. There are $\lvert V \rvert^{2}$ elements in $A$, and $\lvert V \rvert$ elements along the diagonal. The exact number of accesses is therefore $n^{2}-n$. In fact, it will take this long every time.

The worst-case time complexity is therefore $\Theta(n^{2})$

---
c.
I will use the same approach as in my previous algorithm. This time, the array will count the number of edges $(u, v)$ that point towards some node $v$. Once again, it will be a direct access array of size $\lvert V \rvert$, called $PT$.

Looping through each edge $(u, v)$ in $L$, every time $v$ appears, increment $PT[v]$ by 1. Each time $u$ appears, set $PT[u]=-\infty$. At the end of the algorithm if some node $a$ is the leader node, then $PT[a]=\lvert V \rvert-1$.

This occurs because in order for $a$ to be the leader node, there must be no edges $(u, v)$ where $u=a$. Furthermore, the $\lvert V \rvert-1$ nodes must all have edges pointing towards $a$, which will be found in the adjacency list.

In the worst-case, my algorithm will access all the edges in $L$. This will take exactly $\lvert E \rvert$ time. The runtime is therefore $\Theta(m)$.