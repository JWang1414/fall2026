In the lecture, we will attempt to prove that the discovery path $d[v]$ found by BFS is the shortest path from $s$ to $v$ $\delta(s, v)$.

We begin with the observation that $d[v]\geq\delta(s, v)$
- This is trivial

Lemma 1:
> If $u$ enters the queue $Q$ before $v$ during the execution of BFS($s$), then $d[u]\leq d[v]$
- So if some node $u$ is discovered before another node $v$, the discovery path of $u$ is shorter than $v$

Now lets prove the main theorem: After BFS($s$), for every $v\in V$, $d[v]=\delta(s, v)$.

Try proof by contradiction. Suppose that there exists $x \in V$ such that $d[x]\neq\delta(s, x)$. We will choose $v$ the closest node from $s$ such that $d[v]\neq\delta(s, v)$

By the first observation, we therefore have $d[v]>\delta(s, v)$

Now, consider the shortest path from $s$ to $v$ in $G$. This shortest path will have length $\delta(s, v)$. Say $(u, v)$ is the last edge in this path, then we also have:
$$
	\delta(s, v) = \delta(s, u) + 1
$$
Since $v$ comes right after $u$.

Now, recall that we chose $v$ to be the first node such that $d[v]\neq\delta(s, v)$. Therefore, we necessarily have that $d[u]=\delta(s, u)$. Thus, we obtain:
$$
	d[v] > \delta(s, v) = \delta(s, u)+1 = d[u]+1
$$
Keeping this in mind, lets consider the colour of $v$ just before $u$ is explored. It is either white, grey, or black.

If $v$ is white, then $v$ is unexplored. Therefore $d[v]=d[u]+1$

If $v$ is black, then $v$ has already been explored. By lemma 1, $d[v]\leq d[u]$.

If $v$ is grey, then another node $w$ discovered $v$. Then, necessarily, $w$ must have been explored before $u$, and $d[v]=d[w]+1$. So:
$$
	d[w]\leq d[u] \qquad d[v]=d[w]+1
$$
Which tells us that:
$$
	d[v] \leq  d[u]+1
$$
In all cases, we reach a contradiction. Therefore $d[v]=\delta(s,v)$, as needed.

Note: We do not actually need three colours. We only care if a node is white while running BFS. The extra colour (black) was just there to simplify the proof. Now that we are done with this proof, we can go and and remove the colour.
