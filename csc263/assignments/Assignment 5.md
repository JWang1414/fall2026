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
