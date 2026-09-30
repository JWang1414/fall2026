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
My algorithm will search for the greatest key in $B_{1}$, or the smallest key in $B_{2}$. Once this key is found, the node is made into the new root, increasing the height of the tree by one. The two trees are then merged into one BST.
- Explain this with a diagram
## Worst-case running time
For the sake of brevity, I will call the largest key in $B_{1}$ and the smallest key in $B_{2}$ the extrema key/node.

The extrema key in $B_{1}$ can be found by travelling to the right-most node. Similarly the extrema key in $B_{2}$ is found by going to the left-most node. This will take at most $h_{1}$ iterations in $B_{1}$, and $h_{2}$ iterations in $B_{2}$. A loop can be used to traverse both trees at the same time. That same loop may be broken when any extrema key is found. This limits the number of iterations to $\min\{ h_{1}, h_{2} \}$. 

Once the extrema key is found, it is detatched and reattached to become the root node of its tree. Furthermore, the extrema node's subtree must also be reattached to a valid parent. During this process, 2 pairs of pointers are changed. Finally, the two trees are merged together. One new edge is established, between the two trees. This sequence of pointer adjustments takes constant time.

The worst-case run time of the full process is therefore:
$$
	\min\{ h_{1}h_{2} \} + 3 \in O(\min\{ h_{1}h_{2} \})
$$
As needed.
## Justify Correctness
For convenience, I will assume the largest key in $B_{1}$ is found before the smallest key in $B_{2}$. Call this key $m$.

First, $m$ must be removed and made a standalone node. Since $m$ is the largest node in $B_{1}$ it is either a leaf or has just one child. If it is a leaf, remove it, and nothing is changed. If it has one child, remove it, and re-attach its child to its (former) parent. The child essentially takes its place.

$m$ has successfully been made a standalone node, and $B_{1}$ remains a valid BST. Since $m$ is necessarily larger than all keys in $B_{1}$, $B_{1}$ may be connected to the left-side of $m$. This results in yet another valid BST, one where $m$ is now the root node.

Furthermore, because $m$ is also smaller than all keys in $B_{2}$, $B_{2}$ may be attached to the right-side. $B_{1}$ and $B_{2}$ have successfully been merged into a valid BST $T$.

Now, when $m$ is moved to become the root node of $B_{1}$, its height is increased by 1. The re-connection of the orphaned subtree from $m$'s removal will sometimes reduce $B_{1}$'s height by 1, but never increase it. The maximum height of $B_{1}$ after this operation is therefore $h_{1}+1$.

Additionally, when $B_{2}$ is connected to $m$, its height increases by 1. Therefore, the maximum height of $T$ is $h_{1}+1$ or $h_{2}+1$. That is, the height of $T$ is:
$$
	\max\{ h_{1}+1, h_{2}+1 \} = \max\{ h_{1}, h_{2} \}+1
$$
As needed.
- Maybe use a drawing to explain the height of $T$
# Question 3
---
a.
Check if $k$ is greater than the current key $u$. If $k>u$ then move to the right subtree, if $k<u$ then move to the left substree. Repeat this process until $k=u$, then $\text{node}(k)$ has been found, and the process terminates.

After every step, a counter should be incremented by 1 to measure the distance between the root and $k$.

PathLengthFromRoot($root$, $k$)
```
length = 0
u = root
while (k != key(u))
	if k < key(u)
		u = lchild(u)
	else
		u = rchild(u)
	length += 1

# Loop terminates when k = key(u)
return length
```

In the worst-case, the node containing $k$ will be a leaf at the very bottom of the tree. This would take at most $h$ iterations to reach. Worst-case time complexity $O(h)$.

---
b.
Compare $k$ and $m$ with the current key $u$. If $u<k<m$, then move to the right subtree. If $k<m<u$, then move to the left subtree. Repeat this process until $k\leq u\leq m$, then the first common parent of $k$ and $m$ has been found, and the process returns $\text{node}(u)$.

FCP($root$, $k$, $m$)
```
u = root
while (key(u) < k OR m < key(u))
	if (key(u) < k)
		u = rchild(u)
	else
		u = lchild(u)

# Loop terminates when k <= u <= m
return u
```

In the worst-case, $k$ or $m$ could be a leaf node at the bottom of the tree. it would take at most $h-1$ iterations to reach a comment parent. Worst-case time complexity $O(h)$.

---
c.
Use FCP to find the first common parent of $k$ and $m$, I will call it $p$. Then, use PathLengthFromRoot on $k$, $m$, and $p$ to determine their path lengths from root. Then, the path length between $k$ and $m$ is:
$$
	(k_\text{length} - p_\text{length}) + (m_\text{length} - p_\text{length}) = k_\text{length} + m_\text{length} - 2p_\text{length}
$$

PathLength($root$, $k$, $m$)
```
# Find the common parent
p = FCP(root, k, m)

# Determine all path lengths
k_len = PathLengthFromRoot(root, k)
m_len = PathLengthFromRoot(root, m)
p_len = PathLengthFromRoot(root, p)

# Path length between k and m
return k_len + m_len - 2*p_len
```

As established in the previous parts, FCP and PathLengthFromRoot both have worst-case time complexity $O(h)$. The worst-case time complexity of PathLength is therefore:
$$
	O(h) + O(h) + 2 \times O(h) \equiv  O(h)
$$
As needed.
