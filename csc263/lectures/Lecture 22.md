Our goals for today are to:
- Distinguish between algorithm and problem complexity
- Introduce decision trees for comparison-based algorithms
- A lower bound for sorting $n$ distinct integers
# Different Complexity
Suppose we have some computational problem $\mathcal{P}$. The algorithm complexity tells us the cost of some algorithm $\mathcal{A}$. In terms of the running time, comparisons, memory etc.

Problem complexity is the smallest cost that can be achieved by any problem $\mathcal{P}$?
## Sorting Problem
$\mathcal{P}$: sort $n$ distinct integers.

Heapsort and Mergesort take $O(n\log n)$ comparisons in the worst-case. We will show that $\Omega(n\log n)$ is the asymptotic lower-bound on sorting $n$ distinct integers.
- We say Heapsort and Mergesort are asymptotically optimal

We begin by building a model of comparison-based algorithms.

Many familiar algorithms solve problems by comparing input elements. In this case they are just a sequence of comparisons. We will model this behaviour with a *decision tree*.

We will illustrate the idea with Insertion sort.

Say we have $a_{1}, a_{2}, \dots, a_{k}$ are already sorted. Check the next element $a_{k+1}$, and compare it with $a_{k+1}$. If $a_{k+1}<a_{k}$, then compare it with $a_{k-1}$, and so on. Each comparison decides if we make another comparison, or insert $a_{k+1}$ into its properly sorted location.

So for $n=3$ distinct integers $a_{1},a_{2},a_{3}$ insertion sort compares $a_{2}$ with $a_{1}$, then $a_{3}$ with $a_{2}$ and so on. Call this algorithm $\mathcal{A}$. We would like to create a decision tree $T_{\mathcal{A}}$ modelling $\mathcal{A}$.

- Insert an image here

A few things to remark about the decision tree:
1. It is roughly equivalent to the pseudo-code of $\mathcal{A}$ in the sense that you can execute it on any input of size 3
2. The height of $T_{\mathcal{A}}$ is the number of comparisons in the worst-case
3. $T_{\mathcal{A}}$ has a distinct leaf for each permutation of $n=3$ distinct integers

- Missed something here
## Sorting Complexity
Let $\mathcal{A}$ be any comparison-based sorting algorithm which sorts $n$ distinct integers. Let $T_{\mathcal{A}}$ be the decision tree modelling $\mathcal{A}$.

$T_{\mathcal{A}}$ must have a distinct, reachable leaf for each permutation $\pi$ of the integers $1,2,\dots,n$. So $T_{\mathcal{A}}$ must have $n!$ reachable leaves.
$$
	\lvert \text{leaves}(T_{\mathcal{A}}) \rvert \geq n!
$$
Let $h$ be the height of $T_{\mathcal{A}}$. Since $T_{\mathcal{A}}$ is a binary tree, $T_{\mathcal{A}}$ has at most $2^{h}$ reachable leaves.
$$
	\lvert \text{leaves}(T_{\mathcal{A}}) \rvert \leq 2^{h}
$$
Therefore,
$$
	n! \leq \lvert \text{leaves}(T_{\mathcal{A}}) \rvert \leq  2^{h}
$$
Take the logarithm of both sides:
$$
	\log n! \leq  h \implies n\log n \leq  h
$$
So the height of the decision tree is at leave $n\log n$. I conclude that $h=\Omega(n\log n)$ comparisons in the worst-case.