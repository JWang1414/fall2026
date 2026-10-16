Today we continue our discussion of disjoint sets. Recall that we begin with $n$ distinct singleton sets. We would like to implement operations Union and Find.

Our goal is to execute $n-1$ unions mixed with $m\geq n$ finds, and we would like to minimize the total cost.

With the tree structure and "weighted union by size" heuristic established last time, we managed to complete unions in $O(1)$ time, and finds in $O(m\log n)$ time.

The next method we will use the speed up our finds is path compression (PC). Using this method, once we have completed a Find(x), we will adjust the pointer of $x$ and all of its parents to point directly to the set representative.
- Essentially, we must traverse up the path two times. One to find the representative, and one to compress the paths
- The next time we ask to find something in this path, the Find(x) runs in constant time.
- The cost of Find increases the first time, but makes future Finds cheaper. This is called amortization

Now, if we combine WU and PC, does the time complexity of $\sigma$ increase? Recall that we are trying to beat $O(m\log n)$
# Quick Detour
First, we must define the function $2^{*n}$. It is defined recursively,
$$
	2^{*0}=1 \qquad 2^{*n+1}=2^{2^{*n}}
$$
If you cannot tell, this function will blow up almost instantly. $2^{*4}$ is 65536, and $2^{*5}\propto 10^{19729}$.

Now that we understand this, we will now introduce $\log*n$. Which, on the other hand, grows incredibly slowly.
$$
	\log*n = \min\{ k: 2^{*k} \geq  n \}
$$
That is, $\log*n$ is equal to the value of $k$ such that $2^{*k}$ is larger than $n$. So from $n\in[5, 16]$, $\log*n$ is just 3. From $n\in[17, 65536]$, $\log*n$ is just 4. In practice, we will never have a problem large enough to exceed $\log*n$.

So $O(\log*n)$, may as well be constant.
# Time complexity of $\sigma$ with WU and PC
When WU is used in combination with PC, the worst-case time complexity for the forest is $O(m\log*n)$.
- This is a much slower growing function! It may as well be $O(m)$.
- This is incredible. We must complete $m$ Finds. Even if each Find was done in constant time, the time complexity is $\Omega(m)$ just as a trivial lower bound

The proof for this result is out of the scope for this course. Accept it as a theorem.

In fact, it is actually faster than this. The algorithm is known to be $\Theta(m\alpha ^{-1}(m, n))$. The fastest any algorithm can possibly be for this problem. It took 25 years to prove this.
