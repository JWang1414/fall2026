Our analysis today is centred around using DFS as a method for cycle detection.
# White Path Theorem
> For all graphs $G$ and all DFS of $G$, if and only if $v$ becomes a descendant of $u$, then at the time $d[u]$ discovers $u$, there is a path from $u$ to $v$ in $G$ that consists entirely of white nodes

Lets prove this theorem!

Consider any $G$ and any DFS of $G$.

Suppose $v$ is a descendant of $u$ in this DFS. Let $u\to u_{1}\to\dots\to u_{j}\to u_{k}\to v$ be the DFS discovery path from $u$ to $v$.

Well, at the time $d[u]$ when $u$ is discovered, all other nodes on that path have net yet been discovered.
- This is because discovered nodes are not traveled

So, this is an all white path.

Now the other way. Suppose at time $d[u]$ when $u$ is discovered, there is a path from $u$ to $v$ consisting of all white nodes.

To show this, we will try to show all nodes in this path become descendants of $u$. We will use proof by contradiction. Assume there is a some node in the path doesn't become a descendant of $u$.

Call $z$ the closest node to $u$ that is not a descendant of $u$, and $w$ be the node just before $z$. Note that by definition $w$ is a descendant of $u$, or $w=u$.

From here we may uncover a number of facts.
1. $d[u]<d[z]$. That is, $u$ must have been discovered before $z$. The path is white, after all.
2. $d[z]<f[w]$. $z$ is a descendant of $w$, and so $z$ must be discovered for $w$ to be completed
3. $f[w]\leq f[u]$. Which is from the fact that $u$ is a descendant of $w$. Or alternatively $w=u$.

Stringing together these facts we have $d[u]<d[z]<f[u]$.

The only configuration where this is possible is $d[u]<d[z]<f[z]<f[u]$. Which necessarily means that $z$ is a descendant of $u$.
# Theorem 22.11
> For all directed graphs $G$ and all DFS of $G$: $G$ has a cycle $\iff$ DFS of $G$ has a back edge

We begin by assuming the DFS of $G$ has a back edge. $(v, u)$.

Then, necessarily $v$ must be a descendant of $u$. Which, by the White path theorem, means that there exists a path from $u$ to $v$ in the DFS forest. Hence there is a cycle from $u$ to $v$, and back to $u$.

Now, suppose that $G$ has a cycle $C$. Let $u$ be the first node in $C$ discovered by the DFS. Define $v$ to be the node before $u$ in $C$.

Now, at time $d[u]$ when $u$ is discovered, at other nodes in $C$ are white ($u$ is the first to be explored). By white-path theorem, $v$ must be a descendant of $u$ in the DFS.

Hence, when $v$ is explored, $(v, u)$ must also be explored. Since $v$ is a descendant of $u$, $(v, u)$ must be a back edge.
