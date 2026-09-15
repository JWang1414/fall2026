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

Lemma. For an array $A$ of size $n$, $A[n-i+1]=i-1\implies A[n]+A[1]=n-1$. Where $i\in \mathbb{N}$ in $[1, n]$.

Define an array of size $n$. Assume that the elements of this array are defined such that $A[n-i+1]=i-1$, where $i\in \mathbb{N}$ in $[1, n]$.

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

Define an array $A$ of size $n$ such that the elements are $A[n-i+1]=i-1$. Note that this is the negation of the condition inside the inner loop. The inner loop will therefore run to completion, iterating $n$ times.

By the lemma, $A[n]+A[1]=n-1$. The condition in the outer loop is fulfilled, and the loop terminates in constant time.

Since the outer loop will always terminate, $T(n)$ is at least $n$. FREAK is therefore $\Omega(n)$.

Show $O(n)$.
- Split this one into cases

Define an array $A$ of size $n$, $j\in \mathbb{N}$ such that $0<j\leq n$.

Case 1: For all $j$, $A[n-j+1]=j-1$

By the lemma, this also necessitates that $A[n]+A[1]=n-1$. Forcing the outer loop to terminate after running one time. For the same reasons FREAK is $\Omega(n)$, the maximum number of iterations is $n+\text{constant}$.

Case 2: For at least one $j$, $A[n-j+1]\neq j-1$

Then the inner loop, and consequently the function, will terminate in $\leq n$ iterations, without ever making it to the outer loop.

The maximum number of iterations in FREAK is therefore $n$ in the inner loop, and some constant outside this loop. Therefore, FREAK is $O(n)$.

Since FREAK is $\Omega(n)$ and $O(n)$, FREAK is $\Theta(n)$, as needed.
# Question 2
