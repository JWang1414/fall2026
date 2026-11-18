Another intuitive formulation of the MST construction theorem.

Suppose there is some MST $T$ of $G$ which contains the spanning forest $T_{i}$ of $G$. Then, to join the fragments of this forest together, split the forest into one fragment, and the other fragments.

Let $(u, v)$ be an edge of $G$ of minimum weight between the chosen $T_{i}$ and the other trees.
- Complete this later.
# Kruskal's Algorithm
Begin with a list of every edge, sorted from lowest to highest weight. Our current spanning forest is every singleton node. From here, we need to determine what the best choices are.

Well, from the MST theorem, we can connect the first few lowest weight edges, because it is certainly the minimum weight edge between these fragments.

For every minimum weight edge we find, we may join it. However, if we find two nodes $u$ and $v$ in the same set, or fragment, then we reject this edge. This way, we form a minimum weight tree without forming any cycles. Once everything is in the same set, we're done.

- I can add an image here. It was presented in the slides

Some undirected graph might have as many as $n^{2}$ edges. However, to create an MST, we just need $n-1$ edges. Since we are sorting every edge, we may have wasted a lot of work.

- Time complexity analysis here
# Prim's Algorithm
Start from a random node, and extend this node into a bigger and bigger tree. At each step, extend the current tree by selecting the smallest edge out of the tree.