We continue our discussion of balanced BSTs. Last time, our strategy was to use AVL trees for this purpose.

Lets be a little more thorough with our approach of the insertion operation (into a binary tree).

For the purpose of this explanation, lets say we have a +1 node $A$, and another node is added to change it to +2. So the right subtree $B$ is a little heavier. Lets say this subtree has height $h+1$ and the other has height $h$. The subtrees of $B$ must have height $h$
- Note: $B$ cannot be +1 or -1 because the new node $x$ increases the height of $B$. If $B$ has subtrees of height $h$ and $h-1$, then $x$ either wouldn't increase the height of $B$, or unbalance $B$, not $A$.

With the addition of $x$, $B$ has been unbalanced to +1 or -1.

In the first case, we left rotate. After a single left rotation, the BST property is preserved, and the new tree has $B$ at the root with $BF=0$.
- Bonus: The height of this full system remains the same from before $x$ is inserted. So the balance factor for all nodes higher in the tree has not changed. This means we can stop scanning, because the balance of the tree should be maintained beyond this point

In the second case, $B$ has $BF=-1$. We right rotate the left subtree of $B$, and then left rotate the whole system. This is called a Right-left rotation.
- After the double rotation, $x$ may appear in the left or right subtree of the full system. Because of this, the balance factors of the two subtrees ($A$ and $B$ now) will be different in these two cases
	- An implementation of an AVL tree must track this to update the balance factors correctly
- The bonus is also maintained in this case

These two cases can be generalized to all cases that may appear. So we have maintained the BST property in our AVL tree in all cases.
