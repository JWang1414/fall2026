Recall deletes in BSTs. AVL deletes will be relatively similar.

To delete our node, we will search $T$ for the node $x$, and then perform a delete just as we did in a BST.

Just like last time, there are 3 cases.

If $x$ is a leaf, then we can remove it trivially, nothing notable happens.

If $x$ has one child, then we replace $x$ with its child. The child node cannot have a subtree because it would violate the AVL property
- That is, $x$ would be $\pm 2$ unbalanced. So it cannot exist

If $x$ has two children, then we do the same thing as in a BST. Find the successor, swap the two, and them remove $x$. This is actually faster in an AVL tree, since the successor may only have one child with no subtrees.

Once we have done this to remove $x$, we now begin rebalancing the tree.
- Traverse upwards from the removed leaf node
- Re-compute the balance factors
- Re-balance with rotations as needed
