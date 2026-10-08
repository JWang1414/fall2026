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
