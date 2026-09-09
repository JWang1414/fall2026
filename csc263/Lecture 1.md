We begin by defining the worst-case time complexity for an arbitrary algorithm
- This information is review, and neatly summarized in `bounds.pdf`

In plain English, "big O" essentially means that for some input size $n$ and worst-case runtime $T(n)$, $T(n)$ is $O(g(n))$ means that $T(n)\leq g(n)$ within a constant factor, and for sufficiently large $n$.

The definition of $\Omega(g(n))$ is the same, but mirrored with $T(n)\leq g(n)$.

Recall that $O$ and $\Omega$ are essentially an upper and lower bound on the worst-case runtime.

$\Theta(g(n))$ is when $T(n)$ is $O(g(n))$ and $\Omega(g(n))$.
