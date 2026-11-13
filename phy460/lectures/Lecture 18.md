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
