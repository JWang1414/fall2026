# Question 1
---
a.
Lemma: For some number $n$, $\alpha(n+1)=\alpha(n)-(\text{No. carries})+1$.

For convenience, I will call the digit being operated on during addition as the "current digit" or $k$th digit. The $k$th digit always begins with the rightmost digit. For example, in $111+1$, the $k$th digit is initially the rightmost 1 before a 1 is carried over to the middle digit, where the $k$th digit swaps over to the middle one.

Let $n$ be some positive binary integer. Define $\Delta\alpha$ as the change in $\alpha(n)$ after some operation. During the operation $n+1$, there are just two cases:
1. $k$th digit is 0. The operation for the current digit is effectively $0+1$. Trivially, the number of 1's in $n$ increases by 1. $\Delta\alpha=+1$, and the operation terminates, there is no carry on term.
2. $k$th digit is 1. This operation for the current digit is effectively $1+1$. $\Delta\alpha=-1$, however, there is a carry on term for the following digit. Since the following digit may only be 0 or 1, this case reduces to the cases defined here.

A few key observations:
1. There is a carry on term if and only if the $k$th digit is 1.
2. The second case is recursive. When there are numerous 1's in a row, $\Delta\alpha=-1$ for every 1 that is encountered.
3. This process terminates if and only if the $k$th digit is 0.
From observation 1 and 2, this means that $\Delta\alpha=-1$ for every carry on term. And from 3, $\Delta\alpha=+1$ must always happen once. The net change after the full operation is therefore:
$$
	\alpha(n+1) - \alpha(n) = 1- (\text{No. carries}) \implies \alpha(n+1)= \alpha(n) - (\text{No. carries}) + 1
$$
As needed.

Want to show the binomial heap $H$ with $n$ keys has $n-\alpha(n)$ edges. Proof by induction.

Base case: $n=0$ and $n=1$.

In both cases the number of edges is 0.

When $n=0$, $n-\alpha(n)=0-0=0$. When $n=1$, $n-\alpha(n)=1-1=0$. As needed.

Inductive step. Assume the number of edges in $H$ is $n-\alpha(n)$. Want to show that the number of edges in $n+1$ is $n+1-\alpha(n+1)$.

Say we have some heap $H$ with $n$ nodes and $n-\alpha(n)$ edges. Inserting another node, $n\to n+1$ and $\alpha(n)\to\alpha(n+1)$. From the in-class lecture notes, the number of new edges added is equivalent to the number of carry on terms when $H$ is merged with a new node. That is, the number of edges in $H$ is now:
$$
	n-\alpha(n) + (\text{No. carries})
$$
From the lemma:
$$
	\begin{align}
	n+1-\alpha(n+1) & = n+1 - \left[ \alpha(n) - (\text{No. carries}) + 1 \right] \\
	 & = n+1-\alpha(n) + (\text{No. carries}) -1 \\
	 & = n-\alpha(n) + (\text{No. carries})
	\end{align}
$$
- Add a concluding statement and number these equations properly
---
b.
Note that when inserting a new node into a binomial heap $H$ a pairwise comparison is done everytime two trees are merged together. In addition, a tree in $H$ only exists if the associated bit in the binary representation of $n$ is 1. As discussed in part a, if the bit is equal to 1, there must be a carry on term. Therefore, when inserting a new node into $H$, the number of pairwise comparisons is equivalent to the number of carry on terms.

Furthermore, the number of carry on terms is also equivalent to the number of new edges that have been created. I conclude that the cost of insertion, or the number of pairwise comparisons, is equivalent to the number of new edges created.

Let $k$ be the number of new keys inserted into $H$. From part a, the number of new edges created is:
$$
	\left[ n+k - \alpha(n+k) \right] - \left[ n-\alpha(n) \right] = k-\alpha(n+k) + \alpha(n)
$$
Note that the maximum number of 1's in the binary representation of some number $x$ is $\lfloor \log x \rfloor + 1$.
$$
	\leq k - (\lfloor \log(n+k) \rfloor +1) + (\lfloor \log n \rfloor +1) = k-\lfloor \log(n+k) \rfloor  + \lfloor \log n \rfloor
$$
Since $\log n<k$
$$
	< k-\lfloor \log(n+k) \rfloor +k \leq  2k
$$
The average cost of $k$ insertions is therefore $2k /k=2$. As needed.
# Question 2
