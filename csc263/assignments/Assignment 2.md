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
My algorithm will search for the greatest key in $B_{1}$, or the smallest key in $B_{2}$. Once this key is found, the node is made into the new root, increasing the height of the tree by one. Once this is done, the two trees are merged together into a single binary search tree.

Something like this:
```
while (there is a node to the right in B1 OR there is a node to the left in B2)
	Go to the right subtree in B1
	Go to the left subtree in B2

if (largest in B1 was found)
	Detatch the largest node
	Reattach it's left subtree
	Reattach the largest node as the root
	Attach B2 to the largest node
elif (smallest in B2 was found)
	Ditto, with smallest node instead
	...
```
- An image can be included to help the explanation
## Worst-case running time
For the sake of brevity, I will call the largest key/node in $B_{1}$ and the smallest key/node in $B_{2}$ the "extrema" key/node.

The extrema key in $B_{1}$ must be found by searching through the tree. The extrema will always be located in the right-most node, and so can be found by repeatedly traversing to the right until I cannot anymore. In the worst case, this will take $h_{1}$ iterations.

The same process is repeated to find the extrema node in $B_{2}$, which takes similarly takes $h_{2}$ iterations. Since both trees are traversed at the same time, and the loop breaks when any extrema node is found, this will take at worst $\min\{ h_{1}, h_{2} \}$ iterations. Time-complexity $O(\min\{ h_{1}, h_{2} \})$.

Once the extrema key is found, it must be detatched and reattached to the current root node. Furthermore, the extrema node's subtree must also be reattached to a valid parent. This parent will be the extrema node's previous parent. During this process 2 pairs of pointers are changed. Time-complexity $O(1)$.

Finally, the other tree must be merged with the modified tree. One new edge is established, and just one pointer is modified. Time-complexity $O(1)$.

The worst-case run time of the full process is therefore:
$$
	O(\min\{ h_{1}, h_{2} \}) + O(1) + O(1) \equiv O(\min\{ h_{1}, h_{2} \})
$$
## Justify Correctness
Assume $h_{1}\leq h_{2}$. The case when $h_{2}>h_{1}$ is identical, but flipped.

In this case, the search for the largest key in $B_{1}$ is completed first. I will call this key $m$. Since $m$ is larger than any other key in $B_{1}$, the rest of $B_{1}$ may trivially be connected to the left-side of this node. The rest of $B_{1}$ is a valid BST, so the combination of the two results in another valid BST.

The removal of $m$ may result in an orphaned subtree; the original left subtree of $m$. It can be attached to the original parent of $m$.

When $m$ is moved to become the root node, the height of $B_{1}$ increased by 1. It is also possible that the re-connection of the orphaned subtree might decrease $B_{1}$'s height by 1. Overall, the new maximum height of $B_{1}$ is $h_{1}+1$.

Now, $m$ is the root node of $B_{1}$, and has no right subtree. Attach $B_{2}$ here, which itself is a valid BST, and is guaranteed to have values all greater than $m$. Merging $B_{1}$ and $B_{2}$ in this way therefore results in a valid BST, $T$.

Furthermore, the maximum height of $T$ must either be $h_{1}+1$ or $h_{2}+1$. That is, the height of $T$ is:
$$
	\max\{ h_{1}+1, h_{2}+1 \} = \max\{ h_{1}, h_{2} \}+1
$$
As needed.
- Maybe use a drawing to explain the height of $T$
# Question 3
