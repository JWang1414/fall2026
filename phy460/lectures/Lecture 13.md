We have two theorems about fixed points and limit cycles that may help use determine their location.

If we have a simple connected region in a 2D region, where the flow is going inside on all sides of the region, then there is either a fixed point or limit cycle inside.
![[Pasted image 20261027164249.png]]
An example of the above flow.

Alternatively, one might instead use the more powerful Poincare-Bendixson theorem, which is an extension of the above idea.

Poincare-Bendixson Theorem:
> 1. Imagine $R$ is a closed, bounded subset of the plane
> 2. $\dot{\vec{x}}=\vec{f}(\vec{x})$ is a continuously differentiable vector field on an open set containing $R$
> 3. $R$ contains no fixed points
> 4. There exists a trajectory $C$ confined in $R$ such that $C$ begins in $R$ and stays in $R$ for all time
> Then we conclude that $C$ is a closed orbit, or spirals towards a closed orbit as $t\to \infty$. In either case, $R$ contains a closed orbit.

![[Pasted image 20261027164002.png]]
An example of the region $R$ and trajectories of interest inside for the Poincare-Bendixson theorem.

- Interestingly, the Poincare-Bendixson theorem implies that chaos cannot occur in a 2D phase plane
# Lienard Systems
A Lienard equation is a second-order differential equation of the form:
$$
	\ddot{x} + f(x)\dot{x} + g(x) =0
$$
This equation is a generalisation of the van der Pol oscillator $\ddot{x}+\mu(x^{2}-1)\dot{x}+x=0$. Physically, it is like a equation of motion for a unit mass with nonlinear damping force $-f(x)\dot{x}$ and restoring force $-g(x)$.

The equation can be expressed as the system:
$$
	\begin{align}
	\dot{x} & = y \\
	\dot{y} & = -g(x) - f(x)y
	\end{align}
$$
Which will always have a unique, stable limit cycle under the conditions:
1. $f(x)$ and $g(x)$ are continuously differentiable for all $x$
2. $g(-x)=-g(x)$ for all $x$
3. $g(x)>0$ for $x>0$
4. $f(-x)=f(x)$ for all $x$
5. The odd function $F(x)=\int_{0}^{x} f(u) \, du$ has exactly one positive zero at $x=a$, is negative for $0<x<a$, is positive and non-decreasing for $x>a$, and $F(x)\to \infty$ and $x\to \infty$

Using this theorem, one can show that the van der Pol oscillator does indeed have a unique, stable limit cycle.
# Relaxation Oscillations
To begin our examination of nonlinear oscillator, we introduce the van der Pol equation
$$
	\ddot{x} + \mu \dot{x}(x^{2}-1) + x=0
$$
Where $\mu=0$ in simple harmonic oscillation.

Physically, the $x^{2}-1$ term operates as some sort of frictional or driving term, depending on the value of $x$. Then $\lvert x \rvert>1$, it is friction, but when $\lvert x \rvert<1$, it is a driver. In this sense the phase portrait is composed of a stable and unstable spiral, which are resolved with a limit cycle.

Note that:
$$
	\ddot{x} + \mu \dot{x}(x^{2}-1) = \frac{d}{dt} \left( \dot{x} + \mu\left( \frac{1}{3}x^{3}-x \right) \right)
$$
Using the new variables:
$$
	F(x) = \frac{1}{3}x^{3}-x \qquad w=\dot{x}+\mu F(x)
$$
the van der Pol equations becomes:
$$
	\dot{w} = \ddot{x} + \mu \dot{x}(x^{2}-1)=-x
$$
Combining our results yields the system of equations:
$$
	\begin{align}
	\dot{x} & = w-\mu F(x) \\
	\dot{w} & = -x
	\end{align}
$$
And now, applying another change of variablesk $y=w /\mu$,
$$
	\begin{align}
	\dot{x} & = \mu(y-\mu F(x)) \\
	\dot{y} & = -\frac{1}{\mu} x
	\end{align}
$$
![[Pasted image 20261027180138.png]]
Mapping out the nullclines, we find that the trajectory will behave in this manner. Slowly travelling along the cubic line $y=F(x)$, before quickly zipping to the other side.

Generally speaking, the crawls require $O(\mu)$ time, and the jumps require $O(\mu ^{-1})$ time. Seen below
![[Pasted image 20261027180325.png]]
