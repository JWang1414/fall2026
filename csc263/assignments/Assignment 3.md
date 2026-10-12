# Question 1
I begin by defining a helper function MaxBF(u) to calculate the largest imbalance in the BST $T$. Where the imbalance is the absolute value of the balance factor. This simplifies the process because a BST is an AVL tree so long as the imbalance never surpasses 1.

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

MaxBF works by recursively traversing every node in $T$. Once it hits a leaf, it returns a height and an imbalance of 0, 0. Then, it moves up the tree, incrementing the height of the current subtree, and saving the greatest imbalance in the subtree. Once it returns to the root node, it has determined both the height of $T$, but also the largest imbalance in $T$.

Once this is done, all that is left is to say if $T$ is an AVL tree or not.

isAVL(u)
```
return MaxBF(u) < 2
```
## Running time
Given some tree $T$ with $n$ nodes, in order for MaxBF(u) to finish running, it must first recurse through every node in $T$. This is because MaxBF(u) does inorder traversal, going through the left subtrees before moving onto the right.

Since every iteration of MaxBF(u) takes constant time, for MaxBF(u) to finish running through $n$ nodes, it will take $n$ recursions. MaxBF(u) is therefore $\Theta(n)$.

isAVL(u) is nothing but a wrapper around MaxBF(u), and so is $\Theta(n)$ by virtue of this.
# Question 2
---
a.
Define $S$ as a set of integers $i_{1}, i_{2}, \dots, i_{n}$. Where $n=\lvert S \rvert$. In my AVL tree representation of this set, each node will contain:
1. Its value $i_{k}$, which I will use as the key field
2. The sum of all the keys in its left subtree, including itself
3. The number of nodes in its left subtree, including itself

I will assume that the access time for the augmented fields 2 and 3 is $O(1)$.

- Image example included as a file
---
b.
To add the integer $i$ to the set $S$, a node with key $i$ is inserted as normal into the AVL tree. If, at any point, a node is found with the same key $i$, then the program terminates. Assuming a new node is placed, the current sum of itself and its left subtree is $0+i=0$, and the current number of nodes in its left subtree is $0+1=1$. Where the extra value of 1 is added because the node itself is included.

Then, once the node is successfully initialized, the algorithm begin moving up the tree, adjusting the balance factors. Alongside the balance factors, the sum and num values for each node must also be updated. If the new node is in the left subtree of a node, so if $i<\text{current key}$, then the sum and num of the current node is incremented by $i$ and 1, respectively.

Average(t)
```
u = root
sum, num = 0

while (u.key != t):
	if (u.key < t):
		u = u.lchild
	else: // u.key > t
		sum += u.sum
		num += u.num
		u = u.rchild

if (num = 0):
	return 0
else:
	return (sum + u.sum) / (num + u.num)
```

To begin, Average(t) targets the root, and initializes two accumulator variables: sum and num. Then, for the current node $u$, the next step can be split into three cases:
1. If the key of $u$ is less than $t$, then move to the left subtree.
2. If the key of $u$ is greater than $t$, then increment sum and num by the fields saved in $u$. That is, sum is incremented by the sum of all keys in the left subtree of $u$, and num is incremented by the total number of nodes in the left subtree of $u$. Recall that both values include $u$. Once this is done, move to the right subtree.
3. If the key of $u$ is equal to $t$, then we have found the final node. If num is 0, $u$ must possess the smallest key in the tree. The program returns 0 and exits. Otherwise, increment sum and num one final time with the associated fields in $u$ before turning the average and terminating the program.
## Running time
In the worst-case, Add(i) must travel the full height of the tree before going back up again. The main modifications this algorithm makes with Insert(i) is the addition of the sum and num fields, and the maintenence of them as it moves up the tree. The base insertion algorithm takes $O(\log n)$ time (travelling the full height of the tree), and every update to the sum and num fields takes constant time (basic arithmetic). The running time is therefore:
$$
	O(\log n) \times O(1) \in O(\log n)
$$

To compute the average, each accumulation and calculation associated with the average is basic arithmetic, and so takes constant time. In the worst-case, the node with key $t$ is located at the bottom of the tree. Average will take $O(\log n)$ iterations to reach the bottom of the tree, because that is the maximum height of an AVL tree. The worst-case running time in this case is similarly:
$$
	O(\log n) \times O(1) \in O(\log n)
$$
