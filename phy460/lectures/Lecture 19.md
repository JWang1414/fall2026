Today we begin with the discussion of the Lorenz map, and what comes of it.

Maps are characterized by a few properties:
- Use discrete time steps
- Have some variable $x(t)\to x_{n}$, which has a range, like $\mathbb{R}$
- Typically recursively defined $x_{n+1}=f(x_{n})$
- They are deterministic, so $x_{0}\to x_{n}$ $\forall n$

Recall that at one point we used a Poincare map to show the existence of a limit cycle in a problem involving a pendulum. (Lecture 14-15)

- There was a discussion about unimodular maps, but it was heavily dependent on an image. I will include it later
- Analysis of the cobweb construction, and a graphical analysis of their stability

Imagine we have a fixed point on a map $x_{*}=f(x_{*})$ such that $f'(x_{*})\neq 0$. If we begin at some point $x_{*}+\delta$ close to $x_{*}$, but just a little off, then we move to:
$$
	\begin{align}
	f(x_{*} + \delta) & = f(x_{*}) + \delta f'(x_{*}) \\
	 & = x_{*} + \delta f'(x_{*})
	\end{align}
$$
Notice that the distance between the initial point and the fixed point is $\lvert \delta \rvert$. The distance between the two mapped points is $\lvert \delta \rvert\lvert f'(x_{*}) \rvert$. If we have a stable fixed point, then we require:
$$
	\lvert \delta \rvert > \lvert \delta \rvert  \lvert f'(x_{*}) \rvert \implies 1>\lvert f'(x_{*}) \rvert
$$
Which essentially tell us that if $\lvert f'(x_{*}) \rvert$, subsequent points will move closer and closer to the fixed point. Otherwise, they drift away.
