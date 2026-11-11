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
]