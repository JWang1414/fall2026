We have two theorems about fixed points and limit cycles that may help use determine their location.

If we have a simple connected region in a 2D region, where the flow is going inside on all sides of the region, then there is either a fixed point or limit cycle inside.

Alternatively, according to the Poincare-Bendixson theorem, if instead we have an "donut" shape, where the flow is going in on the outside, and going out on the inside, then there must be a limit cycle inside, so long as there are no fixed points inside.

To begin our examination of nonlinear oscillator, we introduce the van der Pol equation
$$
	\ddot{x} + \mu \dot{x}(x^{2}-1) + x=0
$$
Where $\mu=0$ in simple harmonic oscillation.

Physically, the $x^{2}-1$ term operates as some sort of frictional or driving term, depending on the value of $x$. Then $\lvert x \rvert>1$, it is friction, but when $\lvert x \rvert<1$, it is a driver. In this sense the phase portrait is composed of a stable and unstable spiral, which are resolved with a limit cycle.

By considering exclusively the derivative terms in this equation:
$$
	\ddot{x} + \mu \dot{x}x^{2} - \mu \dot{x} = \frac{d}{dt} \left( \dot{x} + \frac{\mu}{3}x^{3}-\mu x \right)
$$
We may define the variables:
$$
	w=\dot{x} + \frac{\mu}{3}x^{3}-\mu x \qquad \dot{w}=-x \qquad F(x) = \frac{1}{3}x^{3}-x
$$
$$
	y=\frac{w}{\mu} \qquad w=y\mu
$$
We can obtain the system of equations:
$$
	\begin{align}
	\dot{x} & = \mu(y - F(x)) \\
	\dot{y} & = -\frac{1}{\mu}x
	\end{align}
$$
In the limit of large $\mu$, $\dot{x}$ is very large, and $\dot{y}$ is very small. What happens is that you shoot over to the nullcline $y=F(x)$, and then get locked into a limit cycle.
