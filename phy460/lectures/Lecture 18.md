Last time we discussed the change of a volume in phase space. Where we have some field $\vec{\dot{x}}=\vec{v}(\vec{x})$. We would that the volume $\Delta ^{n}$ abides by the relation:
$$
	\frac{d}{dt} \Delta ^{n}(t) = (\vec{\nabla}\cdot \vec{v}) \Delta ^{n}(t)
$$
So it is based on the divergence of the vector field.

The Liouville theorem essentially states that for some Hamiltonian flow, the divergence is 0, and so the volume in phase space is constant.

We now roughly introduce the idea of the Poincare reoccurance. Which is a theorem essentially tells us that for a closed system in statistical mechanics, it will eventually reach the initial state again.

One may imagine this as putting a bottle of perfume in a closed-system. The perfume will eventually flow out and evenly fill out the space. The Poincare reoccurance tells us that at some time in the future, the perfume will all end up back in the bottle.
- This will, of course, take incredibly long. It scales exponentially with the number of particles inside of the system.
- It's a property of volume preserving maps

We now introduce the Lorenz equations:
$$
	\begin{align}
	v_{x} = \dot{x} & = \sigma(y-x) \\
	v_{y} = \dot{y} & = rx-y-xz \\
	v_{z} = \dot{x} & = xy-bz
	\end{align}
$$
Where $\sigma, r, b$ are positive, dimensionless parameters. $\sigma$ is the Prandtl number, and $r$ is the Rayleigh number. Physically, $\sigma$ tells us the momentum transfer over heat transfer. $r$ tells us the driving over the dissipation.

We have the $Z_{2}$ symmetry $x\leftrightarrow-x$ $y\leftrightarrow-y$ $z\leftrightarrow z$.

- Missing some content here. Going over some of the basic properties of the Lorenz equations

Computing the divergence of the Lorenz equations:
$$
	\nabla \cdot \vec{v} = -\sigma-1-b <0
$$
So the divergence is negative, and so there is 3D volume contraction.

Due to this volume contraction, quasi-periodic orbits are forbidden.
- Quasi-periodic trajectories must lie on some torus. However, because of volume contraction, 3D objects like this cannot exist

Furthermore, there cannot be any repellers. Since repellers would expand the volume. However, we have already shown the volume contracts.

Now that we have eliminated some possibilities, we begin analyzing the fixed points.

One of them is simply (0, 0, 0).

The linearization around this fixed point is:
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y} \\
	\dot{z}
	\end{bmatrix} = \begin{bmatrix}
	-\sigma  & \sigma & 0 \\
	r & -1 & 0 \\
	0 & 0 & -b
	\end{bmatrix} \begin{bmatrix}
	x \\
	y \\
	z
	\end{bmatrix}
$$
We can see that the $z$ component decouples here. Isolating the system down to just the top-left segment we find the eigenvalues:
$$
	\lambda = \frac{1}{2}(-(1+\sigma) \pm \sqrt{ (\sigma-1)^{2}+4\sigma r })
$$
For $r<1$ the origin is stable, and for $r>1$ the origin becomes a saddle-node.
- Furthermore, note that $\dot{z}=-bz$. So it is always attracting

Another fixed point says:
$$
	\begin{align}
	y & =x \\
	x(r-1-z) & =0 \\
	z^{2} & =bz
	\end{align}
$$
There are two possibilities. $z=0$ or $z=r-1$. In the first case, it reduces back to the origin. In the second, we have
$$
	x=y=\pm \sqrt{ b(r-1) } \qquad z=r-1
$$
Lorenz called these fixed points $C_{\pm}$.

- Missing some content here

Analyzing these two fixed points, we notice that $C_{\pm}$ undergoes the Hopfield bifurcation at,
$$
	r_{H} = r_\text{Hopf} = \frac{\sigma(\sigma+b+3)}{\sigma-b-1}
$$
Which yields the eigenvalues:
$$
	\lambda_{1, 2} = \pm i\sqrt{ b(r_{H}+\sigma) } \qquad \lambda_{3} = -\sigma+b+1
$$
We find that beyond the point where $r>r_{H}$ the fixed points are all unstable. Turns out, the fixed points cover themselves with a limit cycle that doesn't exist in 2D.

It is a semi-stable limit cycle. This is the limit where chaos occurs.

![[Pasted image 20261113222847.png]]
The plot of the fixed points and limit cycles as a function of $r$.

Beyond $r_{H}$ we find that the trajectories are not repelled to infinity, and yet all fixed points and limit cycles are unstable. As it turns out, the trajectories lie on what is called a strange attractor.
# The strange attractor
When Lorenz simulated the equations just within the region where $r>r_{H}$, he found an irregular, aperiodic oscillation that persists for all time.

Visualized in phase space, he found this:
![[Pasted image 20261113223744.png]]
This is the strange attractor. The trajectory lies on this set, and yet never crosses itself. Visualized in 3D, solutions settle onto a perfectly thin set, the attracting zero volume set we were looking for.
![[Pasted image 20261113224003.png]]
However, how can this set exist when two trajectories cannot cross or merge? Well, Lorenz tells us that the two surfaces only appear to merge. Each surface is really a pair of surfaces, and where they merge there are really four surfaces. Continuing this process, we find eight surfaces, before eventually reaching an infinite complex of surfaces, all extremely close to one or the other of two merging surfaces.
- This is the fractal that the strange attractor is comprised of
- The fractal has zero volume, but infinite surface area
# Exponential divergence
Suppose that we have some initial point $\vec{x}(t)$ and $\vec{x}(t)+\delta(t)$, where $\delta$ is a small separation vector. Numerical studies of the Lorenz attractor shows that:
$$
	\lvert \delta(t) \rvert \approx \lvert \delta_{0} \rvert e^{ \lambda t }
$$
Where $\lambda \approx 0.9$. So two neighbouring trajectories separate from each other exponentially fast. That is, until it reaches the other side of the strange attractor.
- The curve is never exactly strange, it just roughly follows this relation.

![[Pasted image 20261113224547.png]]
A plot of the divergence as a function of time $t$. Notice that it will eventually saturate upon reaching the furthest points in the set.

$\lambda$ is sometimes called the *Liapunov exponent*, however, there are actually $n$ Liapunov exponents of an $n$-dimensional system.

Consider the evolution of an infinitesimal sphere of perturbed initial conditions. This sphere will become distorted into an ellipsoid. Define $\delta_{k}(t), k=1\dots n$ as the lengths of the $k$th principal axis of the ellipsoid. Then $\delta_{k}\approx\delta_{k}(0)e^{ \lambda_{k}t }$ where $\lambda_{k}$ are the Liapunov exponents.
- The diameter is controlled by the most positive $\lambda_{k}$
- The $\lambda$ we have identified is merely the largest Liapunov exponent

Based on the Liapunov exponent, we can tell there is some *time horizon* where our predictions will break down
![[Pasted image 20261113225102.png]]

Let $a$ be a measure of our tolerance, where if $\lvert \delta(t_{0}) \rvert\geq a$, our prediction is considered intolerable. Then our predictions break down after:
$$
	t_\text{horizon} \in O\left( \frac{1}{\lambda}\ln\left( \frac{a}{\lvert \delta_{0} \rvert } \right) \right)
$$
# Defining Chaos
There is no agreed upon definition, but there are some working options.

*Chaos* is aperiodic long-term behaviour in a deterministic system that exhibits sensitive dependence on initial conditions.
- Points do not settle into fixed points, periodic orbits, or quasiperiodic orbits
- The system has no random or noisy inputs. Irregular behaviour arises from the system's nonlinearity, not noisy driving forces.
- Nearby trajectories separate exponentially fast
## Defining attractor and strange attractor
An attractor may be roughly defined as a set where all neighbouring trajectories converge. Like a stable fixed point or limit cycle

An attractor $A$ has the properties:
1. $A$ is an invariant set
2. $A$ attracts an open set of initial conditions. That is, it has a basin of attraction
3. $A$ is minimal. There is no proper subset of $A$ that also satisfies conditions 1 and 2

A strange attractor is an attractor which exhibits sensitive dependence on initial conditions.
- Chaotic attractor is sometimes used to emphasize the sensitivity property. Fractal attractor for the geometric property.
