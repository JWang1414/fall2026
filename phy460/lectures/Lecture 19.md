Today we begin with a new class of dynamical systems called maps. Maps are characterised by their use of discrete time steps.

Maps are generally recursively defined $x_{n+1}=f(x_{n})$ where $x(t)\to x_{n}$ has some range, like $\mathbb{R}$. $f$ is some smooth function. They are deterministic in the sense that $x_{0}\to x_{n}$ $\forall n$. So given an initial condition, they will always end up at the same value after $n$ iterations.
- Recall that we used Poincare maps to show the existence of a limit cycle in lectures 14-15. In the textbook this is referred to as the driven pendulum, or Josephson junction.
# Fixed Points and Linear Stability
Suppose $x^*$ satisfies $f(x^*)=x^*$. Then $x^*$ is a fixed point, and the orbit remains at $x^*$ for all future iterations.

To determine the stability of $x^*$ consider the nearby orbit $x_{n}=x^*+\eta_{n}$.
$$
	\begin{align}
	x^*+\eta_{n+1} & = f(x^*+\eta_{n}) \\
	 & = f(x^*) + \eta_{n}f'(x^*) + O(\eta^{2}_{n})
	\end{align}
$$
Where we have used a Taylor series expansion in this last step. Since $f(x^*)=x^*$:
$$
	\eta_{n+1} = f'(x^*)\eta_{n} + O(\eta^{2}_{n})
$$
Neglecting the higher order terms results in the *linearized map*
$$
	\eta_{n+1} = f'(x^*)\eta_{n} = \lambda \eta_{n}
$$
Iterating this relation tells us that $\eta_{n}=\lambda ^{n}\eta_{0}$, and therefore $\lvert \lambda \rvert=f'(x^*)<1$ implies a linearly stable fixed point, and $\lvert f'(x^*) \rvert>1$ is unstable.
- These conclusions about local stability hold for the original nonlinear map
- In the case that $\lvert f'(x^*) \rvert=1$, we must fall back onto higher level terms

Fixed points with $\lambda=\lvert f'(x^*) \rvert=0$ are called super-stable, because perturbations decay like $\eta_{n}\sim \eta ^{(2^{n})}_{0}$ instead of $\eta_{n}\sim \lambda ^{n}\eta_{0}$.
# Cobweb Construction
Graphically, this is the process of drawing a vertical line to $f$, drawing a horizontal line to the diagonal, and repeating this process. Cobwebs let us see global behaviour at a glance.

![[Pasted image 20261125000928.png]]
An example of a cobweb construction for $x_{n+1}=\sin x_{n}$. Note that $\lvert \lambda \rvert=1$ here, and linear analysis is inconclusive. The cobweb construction conveniently informs us that the fixed point $x^*=0$ is globally stable.

A spiralling motion (like the one in $x_{n+1}=\cos x_{n}$) implies that $x_{n}$ converges to $x^*$ through damped oscillations. This is characteristic of fixed points with $\lambda<0$. $\lambda>0$ converge monotonically.

![[Pasted image 20261125001158.png]]
The spiral cobweb construction of $\cos x$.

---
# Class notes
Today we begin with the discussion of the Lorenz map, and what comes of it.

Maps are characterized by a few properties:
- Use discrete time steps
- Have some variable $x(t)\to x_{n}$, which has a range, like $\mathbb{R}$
- Typically recursively defined $x_{n+1}=f(x_{n})$
- They are deterministic, so $x_{0}\to x_{n}$ $\forall n$

Recall that at one point we used a Poincare map to show the existence of a limit cycle in a problem involving a pendulum. (Lecture 14-15)

- There was a discussion about *unimodular maps*, but it was heavily dependent on an image. I will include it later
	- There doesn't appear to be an explanation in the textbook
	- From what I remember, these are maps along the range $[0, 1]$. Maps are unimodular when they send to 0 at $x=0$ and $x=1$.
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