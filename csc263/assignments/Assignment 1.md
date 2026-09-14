# Question 1
Rough work:
$$
	A[n-j+1] = j-1
$$
$$
	A[n-1+1] = 1-1 \implies A[n]=0
$$
$$
	A[n-2+1] = 2-1 \implies A[n-1]=1
$$
$$
	A[n-n+1] = n-1 \implies A[1] = n-1
$$
$$
	A[n-(n-1)+1] = (n-1)-1 = A[n-n+1+1] = A[2] = n-2
$$
$$
	A[n] + A[1] = 0 + n-1=n-1
$$
$$
	A = \{ n, n-2, n-3, \dots, 2, 1, 0 \}
$$
---
Want to show that the time complexity $T(n)$ is $\Theta(n)$.

Lemma. $A[n-i+1]=i-1\implies A[n]+A[1]=n-1$
- Express this portion a little more formally

Define an array of size $n$ with indices $i$. Assume that the elements of this array are defined such that $A[n-i+1]=i-1$.

When $i=1$,
$$
	A[n-1+1] = 1-1 \implies A[n]=0
$$
When $i=n$,
$$
	A[n-n+1] = n-1 \implies A[1] = n-1
$$
Therefore,
$$
	A[n] + A[1] = 0 + (n-1) = n-1
$$
As needed.

Show $\Omega(n)$.

Define an array $A$ of size $n$ such that the elements are $A[n-i+1]=i-1$. Note that this is the negation of the condition inside the inner loop. The inner loop will therefore always run $n$ times.

By the lemma, however, $A[n]+A[1]=n-1$. The condition in the outer loop is fulfilled, and the function terminates in constant time.

Therefore, FREAK may run at least $n$ iterations. $\Omega(n)$

Show $O(n)$.
- Split this one into cases

Define an array $A$ of size $n$.

By observation, the inner loop will only complete all iterations if and only if $A[n-j+1]=j-1$. Where $j\in \mathbb{Z}$ ranges from $[1, n]$. Otherwise, the loop, and consequently the function, will terminate pre-maturely.

However, by the lemma, this also necessitates that $A[n]+A[1]=n-1$. Forcing the outer loop to terminate after running one time.

In the alternative case where $A[n-j+1]\neq j-1$, and the condition in the inner loop is not satisfied, the loop will once again terminate early in $\leq n$ iterations.

The maximum number of iterations in FREAK is therefore $n$ in the inner loop, and 1 in the outer loop. $O(n)$

I conclude that FREAK is $\Omega(n)$ and $O(n)$. FREAK is therefore $\Theta(n)$, as needed.
# Question 2
