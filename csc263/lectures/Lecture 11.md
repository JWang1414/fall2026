Today with discuss disjoint sets. Imagine we have $n$ distinct elements, each in their own singleton sets.

Label these sets $S_{i}$ from 1 to $n$. Each set has a representative element to identify the set. $S_{x}$ is the set represented by $x$.

The operations we want are:
- Union(x, y) where $x$ and $y$ are two distinct representatives
	- Can be done at most $n-1$ times given $n$ sets
- Find(x) searches for the set that contains $x$. It returns the representative of that set

Say we have some sequence $\sigma$ with $n-1$ unions and $m\geq n$ finds. We would like to find a method to minimize the total cost of such operations.
## Candidate: Linked List
Say each set is represented as a linked list. We will choose the head as the representative, since it's convenient.

Union for two linked lists is $O(1)$ time. Which is nice. But Find is $O(n)$, since we need to search through the whole list.

The running time is:
$$
	1 \times (n-1) + m \times n \in O(mn)
$$
That's pretty bad, worse than $O(n^{2})$

To solve this issue, one might try to augment the data structure so each element has a pointer to the head. In this case, find is $O(1)$. But on the other hand, for each Union, all the pointers must be updated to point to the new head. So Union is now $O(n)$. They've just been swapped.

Okay, lets try a little more with the linked list. What happens if, during a union, we always choose to union the smaller list with the larger one? Then we need to update less pointers. In the worst case, we need to join $n /2$ and $n /2$ elements. This is still $O(n)$ time.
- In the tutorial, we will show that the total time for sequence $\sigma$ is actually $O(m+n\log n)$
## Candidate: Forest Structure
Every set is represented by a tree, and each non-root node points to its parent. They do not track their children. The root node is therefore the representative.

These trees have no constraints. They aren't BSTs.

For Find, given a pointer to $x$, we get the representative by moving up until we reach the root node.

To Union two sets, just add one of the provided representatives as a child to the other one. This is done in $O(1)$ time.

What's the running time for Find? It depends on the length of the path.

What is the worst case for $\sigma$? Imagine you Union everything, and then do your $m$ finds. In the worst case, Find takes $n$ time. In this example we have $\Omega(mn)$ time.

To speed this up, we will try a "weighted union by size" heuristic. Intuitively, we should try to make smaller trees the children of bigger tree.
- Any tree $T$ under this rule will have height at most $\log n$.
- In this version the running time is $O(m\log n)$
### Whys is it $\log n$?
Lemma: With WU, any tree $T$ of height $h$ created during $\sigma$ has $\lvert T \rvert \geq 2^{h}$
- Where $\lvert T \rvert$ is the size or number of nodes in $T$

Proof by Induction. Base case: $h=0$
- A tree with $h=0$ has $2^{0}=1$ nodes. As needed.

Inductive step: Assume the lemma holds for trees of height $h\geq 0$. What to show this implies it hold for $h+1$. That is, for a tree with $2^{h+1}$ node.

Say we have two trees $A$ and $B$. $A$ has height $h$, and we would like to attach $A$ to the larger $B$. By the induction hypothesis, $\lvert A \rvert\geq 2^{h}$. Furthermore, since $\lvert B \rvert \geq \lvert A \rvert$ we also have $\lvert B \rvert\geq 2^{h}$. The total number of nodes is therefore:
$$
	\lvert T \rvert \geq  2^{h} + 2^{h} = 2^{h+1}
$$
As needed.

Now, since we have $n$ union, trivially $\lvert T \rvert\leq n$. From this fact the following easily follows:
$$
	2^{h}\leq  \lvert T \rvert \leq  n \implies h \leq  \log n
$$
Where we have taken the log of both sides.
