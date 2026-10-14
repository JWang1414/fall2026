# Question 1
I begin by defining a helper function MaxBF(u) to calculate the largest $\lvert BF \rvert$ in the BST $T$. Where $\lvert BF \rvert$ is simply referring to the absolute value of the balance factor. Using this quantity, a BST is an AVL tree so long as $\lvert BF \rvert<2$.

MaxBF(u)
```
hleft, hright, leftbf, rightbf = 0

// Determine the height and balance factors of the subtrees
if (u.lchild is not nil):
	hleft, leftbf = MaxBF(u.lchild)
	hleft += 1
if (u.rchild is not nil):
	hright, rightbf = MaxBF(u.rchild)
	hright += 1

// Compute the height and balance factor for the current node
hcurrent = max(hleft, hright)
currentbf = abs(hleft - hright)

return hcurrent, max(currentbf, leftbf, rightbf)
```

MaxBF works by recursively traversing every node in $T$. Once it hits a leaf, it returns $(\text{Height}, \lvert BF \rvert)=(0, 0)$. Then, it moves up the tree. For each node, it increments the height of the current subtree by 1, and stores the $\max\{ \lvert BF \rvert \}$ in the current subtree. These are the two invariants in the algorithm. Once it has returned to the root node, these two quantities are equivalent to the height of $T$, and $\max\{ \lvert BF \rvert \}\in T$.

Now, all that is left is to say is if $T$ is an AVL tree or not.

isAVL(u)
```
height, bf = MaxBF(u)
return bf < 2
```
## Running time
Given some tree $T$ with $n$ nodes, in order for MaxBF(u) to finish running, it must first recurse through every node in $T$. This is because MaxBF(u) does inorder traversal, going through the left subtrees first before eventually finishing at the right-most node.

MaxBF(u) is composed entirely of arithmetic and conditionals, so each iteration of MaxBF(u) takes constant time. For MaxBF(u) to finish running through $n$ nodes, it will take $n$ recursions. Its running time is:
$$
	n \times \text{const.} \in\Theta(n)
$$
isAVL(u) is nothing but a wrapper around MaxBF(u). I conclude the full algorithm completes in $\Theta(n)$ time.
# Question 2
---
a.
Define $S$ as a set of integers $i_{1}, i_{2}, \dots, i_{n}$. Where $n=\lvert S \rvert$. In my AVL tree representation $T$, each node $u$ will contain:
1. Its value $i_{k}$, which I will use as the key field
2. The sum of all the keys in $u$ and its subtrees
3. The number of nodes in $u$ and its subtrees

Under each node $u$ is the sum of the keys in its subtrees (including itself) $u_{\Sigma}$, and the number of nodes in its subtrees (including itself) $u_{\eta}$. Written out in $(u_{\Sigma}, u_{\eta})$ form.

- Image example included as a file
---
b.
For some node $u$, I will refer to the sum of all the keys its subtrees as $u_{\Sigma}$, and the number of nodes in its subtrees as $u_{\eta}$. Recall that both $u_{\Sigma}$ and $u_{\eta}$ include $u$ itself in their calculations.

To add the integer $i$ to the set $S$, a node $u$ with key $i$ is inserted as normal into the AVL tree. (Traverse to the bottom, and insert $u$ as a leaf). If, at any point, an existing node is found with the same key $i$, then the program terminates. Assuming a new node is placed, because it is a leaf, $u_{\Sigma}=i$ and $u_{\eta}=1$.

Once $u$ is placed, the algorithm can begin moving up the tree, adjusting the balance factors. Alongside the balance factors, $a_{\Sigma}$ and $a_{\eta}$ must be updated for each node $a$ that is passed through moving up the tree, up until the root node. Furthermore, they must also be changed whenever the balance factors are changed. For example, during a rotation.

Say we have some parent node $a$ with children $b$ and $c$. Then $a_{\Sigma}=b_{\Sigma}+c_{\Sigma}+a.\text{key}$ and $a_{\eta}=b_{\eta}+c_{\eta}+1$. Notice that these are basic arithmetic operations, and so can be completed in constant-time.

Average(t)
```
u = root node
sum, num = 0
lessthan = True

while (u.key != t):
	if (u.key < t):
		if (lessthan):
			sum += u.sum
			num += u.num
			lessthan = !lessthan
		u = u.rchild
	else:
		if (!lessthan):
			sum -= u.sum
			num -= u.num
			lessthan = !lessthan
		u = u.lchild

if (lessthan):
	sum += u.sum
	num += u.num
if (u.rchild is not nil):
	sum -= u.rchild.sum
	num -= u.rchild.num

if (num <= 1):
	return 0
else:
	return sum / num
```

To compute Average(t), the algorithm requires the sum of all values $\leq t$, and the number of values $\leq t$. To accomplish this, Average(t) searches for the key $t$, while swapping between two modes:
1. Searching for less than mode. Initially, Average(t) will search for some node $u.\text{key}<t$. When $u$ is found, two accumulator variables $\Sigma$ and $\eta$ are incremented to $\Sigma+u_{\Sigma}$ and $\eta+u_{\eta}$. At this point it swaps to the second mode.
2. Searching for greater than mode. Once the first mode has been completed, Average(t) will begin searching for $u.\text{key}>t$. When $u$ is found, the two accumulator variables are decremented to $\Sigma-u_{\Sigma}$ and $\eta-u_{\eta}$. It then swaps back to the first mode.

In this manner, Average(t) will systematically count all keys $<t$ and remove all keys $>t$. Once that is done, $u$ is the node with key $t$, and some clean up is necessary. If the algorithm is in mode 1, then the sum of $u$ must be added to $\Sigma$, because it has not been included yet. If $u$ has a right subtree, then the sum of that right subtree must be removed from the $\Sigma$, because those keys are $>t$. Once this is done, the average is computed and returned. In the event where just a single node has been counted, 0 is the result, because there are no keys $<t$.
## Running time
In the worst-case, Add(i) must travel the full height of the tree before going back up again. The main modifications this algorithm makes with the base Insert(i) is the addition of the sum and num fields, and the maintenence of them as it moves up the tree. The base insertion algorithm takes $O(\log n)$ time (travelling the full height of the tree), and every update to the sum and num fields takes constant time (basic arithmetic). The running time is therefore:
$$
	O(\log n) \times O(1) \in O(\log n)
$$
To compute the average, each accumulation and calculation associated with the average is basic arithmetic, and so takes constant time. In the worst-case, the node with key $t$ is located at the bottom of the tree. Average(t) will take $O(h)$ iterations to reach the bottom of the tree, where $h$ is the height of the tree. Since $T$ is an AVL tree, the worst-case running time in this case is similarly:
$$
	O(\log n) \times O(1) \in O(\log n)
$$
# Question 3
---
a.
Define a hash table $\beta$ of size $m\propto n$ (with chained, or linked list entries). Assume this hash table uses a constant-time SUHA hash function. The entries in $\beta$ are identical to the entries in $B$. This may be accomplished by hashing each entry in $B$ to $\beta$.

Now, to count the size of the set $D$, loop through the entries of $A$, and search for them in $\beta$. Define the accumulator variable $a=0$. If some entry $A[i]\in \beta$, then $a$ remains unchanged. If $A[i]\not\in \beta$, then $a$ is incremented to $a+1$. When all entries in $a$ have been looped through, return $a$.

NoOverlap(A, B)
```
// Hash the values of B into beta
beta = Hash table of size m
for entry in B:
	beta.insert(entry)

// Compute the size of the set D
a = 0
for e in A:
	if e is NOT in chain beta[hash(e)]:
		a += 1

return a
```
---
b.
Assume a constant-time SUHA hash function that evenly distributes entries in $\beta$. I also assume $m\propto n$ or $m\in \Omega(n)$ so that the chains in $\beta$ are short. The combination of these assumptions results in expected constant-time searches through $\beta$.

To hash the values of $B$ into $\beta$:
1. $\beta$ is initialized as an empty hash table
2. All $n$ entries in $B$ are looped over and hashed into $\beta$. From my assumption of constant-time SUHA, each insert takes constant time.

The running time of this step is:
$$
	1+ \underbrace{ n\times 1 }_{ n\text{ hashes} }= n+1 \in O(n)
$$

To compute the size of the set $D$:
1. $a$ is initialized at 0
2. All $n$ entries in $A$ are iterated over
3. If the entry $e$ is not found to be inside $\beta$, then $a$ is incremented by 1. Recall that my assumptions result in constant-time searches through $\beta$.

The running time of this step is:
$$
	1+\underbrace{ n\times 1 }_{ n\text{ searches} } = n+1 \in O(n)
$$
The time complexity of the full algorithm is therefore:
$$
	O(n) + O(n) \implies O(n)
$$
---
c.
In the worst-case, all entries from $B$ are hashed into the same bucket in $\beta$. This results in a chain of length $n$, with associated search time $O(n)$.

Hashing the values from $B$ into $\beta$ remains the same, and runs in $O(n)$ time. However, since searching is now $O(n)$, the worst-case running time of the second step is modified to:
$$
	1 + n \times n = n^{2}+1 \in O(n^{2})
$$
For example, imagine if all the values in $A$ and $B$ hash to the same bucket. However, none of the values in $A$ are in $B$. Then, for each search, the entire chain at this bucket must be looked through before verifying that $e$ is indeed not in $\beta$ (and by extension $B$). This means for each of the $n$ entries in $A$, the search takes at least $n$ iterations. The running time is therefore at least:
$$
	1+n\times n = n^{2}+1 \in \Omega(n^{2})
$$
I conclude:
$$
	O(n^{2}) \wedge \Omega(n^{2}) \implies \Theta(n^{2})
$$
