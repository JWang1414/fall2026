We continue our discussion of the index today.

Last time, we had a discussion showing that the index $I$ around some closed loop $C$ is:
$$
	I(C) = \frac{1}{2\pi} \oint d\theta
$$
The integral here will always be some $2\pi n$, where $n$ is an integer, because the vectors must return to their original state. So this basically just tell us that the index is the $n$ rotations that are made around the loop.

We may go further and claim that the index is:
$$
	I(C) = \frac{1}{2\pi} \int_{C} \frac{v_{x} \, dv_{y} - v_{y} \, dv_{x}}{\lvert v \rvert ^{2}}
$$
Which is just the expanded version of what we had defined earlier.

Index properties:
1. If no zero of $\vec{v}$ inside $C$, then $I(C)=0$
2. Topologically invariant

Reminder:
$$
	\oint_{C} \vec{A}\cdot d\vec{l} = \int_{S} (\nabla \times \vec{A})\cdot d\vec{S}
$$
Where $C$ is some closed loop and $S$ is the surface enclosed by this loop.

Discussion of the winding map from $S^{n}\to S^{n}$. Where $S^{n}$ is a sphere in $\mathbb{R}^{n+1}$. So $S^{0}$ is two points, $S^{1}$ is a circle, and $S^{2}$ is a sphere.

These maps are useful for defining domain walls, vertices, monopoles, and instoutons... (not sure what these are)

We now return to the 1D ising model. We have our familiar spins, and two spins next to each other would like to have nearby spins the same. The energy is:
$$
	H = -\lvert J \rvert \sum_{\left< ij \right> }S_{i}S_{j}
$$
The ground states have everything pointing down or up.

In this system there are two $S^{0}$, $\pm \infty$ and the two ground states.
- Note that a sphere is defined to be the points equidistant from the origin. Which is why it's just two points in 1D.

The lowest energy excitation is when one atom is flipped relative to the ground state. This one flipped atom is called the "*magnon*". It can "move" because the magnon can be any atom. They all have the same energy.

Another possible state is all down on the left, and all up on the right. This is called a *kink*, or *topological soliton*.

One can imagine mapping these infinities to the up or down spin. This is essentially just a map from two points to two points. $S^{0}_{\infty}\to S^{0}_\text{vac}$

Magnons cost a finite energy to destroy, or flip back. You cannot destroy a kink, because there is an infinite number of spin up/downs. You need infinite energy.
- The case with the magnons is called *topologically trivial*, and the case with the kinks is called *topologically protected*
- The second is called a *topological soliton* because it cannot be easily destroyed

One can further imagine stretching the ising model with a kink into 2D. Then, the swap from up to down becomes a line. Everything on the left of the 2D plane is up, and on the right is down. Replicate this in 3D, and it becomes a surface. This break between up and down, whether it be a line or surface, is what we call a *domain wall*.

This is a continuum mock-up of the ising model:
$$
	E = \int \left( \frac{1}{2}\left( \frac{ \partial \phi(x) }{ \partial x } \right) ^{2}+\frac{\lambda}{4}(\phi^{2}(x)-1) \right) \, dx
$$
See that the energy is lowest when,
$$
	E=0 \implies \phi^{2}-1=0 \implies \phi = \pm 1
$$
Which are the ground states. Furthermore,
$$
	\frac{ \partial \phi }{ \partial x } =0
$$
The combination of these conditions is intended to tell us that $\phi$ will eventually be some constant with $\pm 1$, because this is the case when $E$ is finite.

Now lets expand this model into 2D, so that we have $S^{1}_{\infty}\to S^{1}_\text{vacua}$.
$$
	E = \iint (\nabla \phi)(\nabla \phi)^* + \lambda(\phi^*\phi-1)^{2} \, dx \, dy
$$
Which once again tells us that for finite energy $\lvert \phi \rvert=1$ and $\phi=\text{const.}$ So the ground states form a circle in this plane.

We say that the space of the vacua $S^{1}_{\phi_{1}}$ is $\lvert \phi \rvert=1$. Non-trivial maps $S^{1}\to S^{1}_{\phi}$ exist.
$$
	\phi|_{\lvert \vec{x}\to \infty \rvert } = e^{ in\theta }
$$
Something about how winding in $\phi$ will result in $n$ winds in the map.
