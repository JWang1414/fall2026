# Question 4
---
a.
If $k\leq x.key$, them the algorithm terminates.

Otherwise, increase $x.key$ to $k$. Swap $x$ with its parents until the max heap ordering is once again maintained.

The height of this binomial tree within the binomial max heap is at most $\log n$, so the running time of this process is $O(\log n)$.

---
b.
For some node $x$ in a binomial tree $B_{k}$, use part a to increase $x.key$ to some value $k$ that is greater than $root.key$ for $B_{k}$. Then, $x$ is the new root node.

Now, remove $x$ from $B_{k}$. By the properties of binomial trees, $B_{k}-\{ x \}$ is another binomial max heap. Union the remainder of $B_{k}$ with the rest of the heap $H-B_{k}$.

Increasing $x.key$ to $k$ and moving it up $B_{k}$ will take $O(\log n)$ time, as shown in part a. The removal of $x$ can be done in constant time. Then, Union takes at most $O(\log n)$ time (from lecture notes). The running time is:
$$
	O(\log n) + O(1) + O(\log n) \implies O(\log n)
$$
## Part 2
- The idea that's being requested of me in this question is to use one heap, and remove the minimum values by shifting them to the top before removing them, which was done in part 1. However, I have no idea how to maintain a mechanism that would work in $O(\log n)$ time.
- The easiest solution I can think of that fulfills the requirements is using two binomial heaps. A max and min ordered one. But that doesn't use part 1 at all
	- In this case, the implementation of all the operations is trivial. It just takes up double the memory