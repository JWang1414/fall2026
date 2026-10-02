Today we will be discussing augmented data structures. Lets say you want to book a conference, how do we check if there are conflicts?

If we have some intervals $i$ and $i'$, then define $i$ as the range from $(low[i], high[i])$. Then we know there's an overlap if $low[i]<high[i']$, where $i'$ is the event that comes before.

We would like to support insert(x), delete(x), and search(x). We would also like to display intervals that overlap with $x$.

For this purpose, we will use AVL trees, because they share an innate ordering with the problem of interest.

Each node stores the low and high end of $x$. The low end will be the key of the node. In addition to this data, we will also store $max(x)$, the largest value of $high(x)$ in the subtree of $x$, including itself
- In the future, this will help us determine where to search for conflicts

So how can we maintain this efficiently? Well, assuming we know the max values of $x$'s children, then this is simply:
$$
	\max(x) = \max(\text{high}(x), \max(\text{left}), \max(\text{right}))
$$
Which can be done in $\Theta(1)$ time!

If we insert a new node, or delete a node, we can do so using the typical AVL tree mechanism. Then, while we're travelling up the tree and balancing everything, we can also update the max in $\Theta(1)$ time.

Now, when we search, we would like to find the first element that overlap with $x$.

Search(x)
```
y = root
while (y != null AND y and x don't overlap)
	if (y.left = null OR max[y.left] < low[x])
		y = y.right
	else
		y = y.left
return y
```

So what is this doing in english?
- First, if we are at a leaf, or $y$ and $x$ overlap, then break, we are done
- Now, if the left subtree exists, and the max in the left subtree is less than $\text{low}(x)$, then there's nothing in the left subtree than can overlap with $x$. Go to the right
- Otherwise, there's something in the left subtree that overlaps with $x$. We need to find it. So go to the left.
