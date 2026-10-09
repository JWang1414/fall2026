# Randomized Quicksort
Given some set $S$ of $n$ distinct keys, output the keys of $S$ in increasing order.

In essence, this algorithm is the typical divide and conquer recursive algorithm Quicksort uses, but with a pivot that is selected uniformly at random.
# Complexity Analysis
Fix some input $S$ with $n$ distinct keys.

Let $C$ be the number of key comparisons done by randomized quicksort RQS(S). What is the worst case value of $C$?

Well, just to start, we pick a random pivot and compare it with everybody else. This takes $n-1$ operations. Now, in the worst case, the next one will take $n-2$ operations.

So in the worst case:
$$
	C=(n-1) + (n-2) + \dots = \frac{n(n-1)}{2} \in \Theta(n^{2})
$$
But what is the expected average for $C$?

Let $z_{1}<z_{2}<\dots<z_{i}<\dots<z_{j}<\dots<z_{n}$ be the keys in $S$. Sorted in ascending order. Note that RQS(S) compares $z_{i}$ and $z_{j}$ at most one time, if and only if one of the two is selected as a pivot.

We'll define an indicator random variable $c_{ij}$
$$
	c_{ij} = \begin{cases}
	1 & z_{i} \text{ and } z_{j} \text{ are compared} \\
	0 & \text{otherwise}
	\end{cases}
$$
See that the total number of comparisons is:
$$
	C = \sum_{1\leq  i<j\leq  n} c_{ij}
$$
We would not like to compute the expectation value:
$$
	E(C) = E\left( \sum c_{ij} \right) = \sum E(c_{ij})
$$
The expectation value for each $c_{ij}$ is:
$$
	E(c_{ij}) = 1(Pr(c_{ij}=1)) + 0(Pr(c_{ij}=0)) = Pr(z_{i}\text{ and }z_{j}\text{ are compared})
$$
We will later prove that this probability is $2 /(j-i+1)$.

The expected running time is therefore:
$$
	E(C) = \sum_{1\leq i< j\leq n} \frac{2}{j-i+1} \leq  2n \left( 1+\frac{1}{2} + \frac{1}{3} + \dots + \frac{1}{n} \right)
$$
This second portion is the harmonic series, which is $O(\log n)$. So the expected complexity of randomized quicksort is $O(n\log n)$.
# Showing the probability
So how did we know that the probability those two would be compared is $2 /(j-i+1)$?

Consider the subset of keys $Z_{ij}=\{ z_{i}, \dots, z_{j} \}$. See that $\lvert Z_{ij} \rvert=j-i+1$.

RQS(S) will continuously selects pivots to split $S$. Until it has subsets of size 0 or 1.

Now, so long as RQS(S) chooses pivots that are not in $Z_{ij}$, then $Z_{ij}$ remains a subset formed by the pivots. $z_{i}$ and $z_{j}$ have not yet been compared.

However, because $\lvert Z_{ij} \rvert>1$, at some point RQS must select a pivot inside. At this point, there are two cases:
1. The pivot is not $z_{i}$ or $z_{j}$. They will never be compared
2. The pivot is $z_{i}$ or $z_{j}$. They will be compared

So the probability that $z_{i}$ and $z_{j}$ are compared is equivalent to the possibility $z_{i}$ or $z_{j}$ are selected as a pivot in $Z_{ij}$. This chance is:
$$
	\frac{2}{\lvert Z_{ij} \rvert } = \frac{2}{j-i+1}
$$
This holds because:
- The chance to pick anyone in $Z_{ij}$ is equal
- The exact proof required conditional probability, but we will not cover it