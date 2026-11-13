Today we introduce and discuss topological sort. Say we have some project where some tasks must be done before others. In what order should we complete the tasks?

To model this problem, we represent the project as some graph $G$. Each node is a task, and a directed edge $(u, v)$ tells us that $u$ must be done before $v$.

Notice that if there is a cycle, then the project is impossible to complete. So we will assume directed acyclic graphs (DAGs).

Now, to reformulate our question: What is an ordering of vertices such that for every edge $(u, v)$, $u$ appears before $v$.

To accomplish this, we define topological sort as follows:

TopologicalSort(G)
```
Call DFS(G) to compute finishing times
As each vertex finishes its DFS, it is added to the beginning of a linked list
Output the linked list
```

This has worst case running time $O(\lvert V \rvert+\lvert E \rvert)$. This is derives from the cost of the DFS.

How can we be sure that this will produce a topological sort of $G$?

We begin by noting a few things:
- The algorithm lists nodes in decreasing order of $f[v]$
- For each edge $(u, v)$, $f[u]>f[v]$
# Proof 1
Consider the state of $v$ just before exploring $(u, v)$. $v$ must be either grey, white, or black.

However, $v$ may only be grey if we have a back edge, since we must be exploring some ancestor of $v$ for this to occur. This contradicts our assumptions, and so cannot happen.

If $v$ is white, then $v$ is a descendant of $u$. By definition we have $d[u]<d[v]<f[v]<f[u]$ and so $f[u]>f[v]$. As needed.

If $v$ is black, then $v$ has already been explored, but $u$ has no. So, trivially, $f[u]>f[v]$. As needed.

So for every directed edge $(u, v)$, $u$ will be listed before $v$.
# Proof 2
This proof instead uses the classification of $(u, v)$.

Recall that back edges are not possible.

For forward and tree edges, $u$ is an ancestor of $v$, so we must have:
$$
	d[u]<d[v]<f[v]<f[u]
$$
Which is exactly what we are trying to show: $f[u]>f[v]$.

What about if $(u, v)$ is a cross edge? Well there are two cases:
$$
	d[u]<f[u]<d[v]<f[v] \qquad d[v]<f[v]<d[u]<f[u]
$$
- The proof is shown in the second case, but not in the first. I didn't quite catch why we can throw out the first case.
