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

Magnons cost a finite energy to destroy, or flip back. You cannot destroy a kink, because there is an infinite number of spin up/downs. You need infinite energy.