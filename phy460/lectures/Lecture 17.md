We begin with an aside: how does a volume evolve along a flow? Specifically what is the change in the volume?

Say we have some flow $\dot{x}=\vec{v}(\vec{x})$ where $\vec{x}\in \mathbb{R}^{n}$. The Liouville theorem tells us that a Hamiltonian flow preserves volume.

Note that for some matrix $a_{ij}$, the determinant is:
$$
	\det(a_{ij}) = \sum_{i_{1}, \dots, i_{n}=1}^n \epsilon_{i_{1}\dots i_{n}} a_{1, i_{1}} a_{2, i_{2}}\dots a_{n, i_{n}}
$$
- In this class $a_{ij}$ will notate the $j$th component of the $i$th vector.

Recall that $\det(a_{ij})$ is the volume of the $n$-dimensional parallelopiped.

Now, say we have represented $a_{ij}$ in the form:
$$
	a_{ij} = \delta_{ij} + \varepsilon b_{ij}
$$
Where $\delta_{ij}$ is the identity matrix, and $\varepsilon\ll1$. Then,
$$
	\det(\delta_{ij}+\varepsilon b_{ij}) = 1 + \varepsilon \text{trace}(b) + O(\varepsilon^{2})
$$
The trace is simply $\sum_{i}b_{ii}$.

Apply this to the volume we had earlier. Imagine we have some vectors initially at $\vec{x}(t)$ and $\vec{x}(t)+\vec{e}_{i}\Delta$. Then after some small amount of time $\delta t$
$$
	\vec{x}(t) \to \vec{x}(t) + \vec{v}(\vec{x}(t))\delta t
$$
$$
	\vec{x}(t)+\vec{e}_{i}\Delta \to \vec{x}(t)+\vec{e}_{i}\Delta \vec{v}(\vec{x}+\vec{e}_{i}\Delta) \delta t
$$
Where you can see their propagation in time is simply decided by $\vec{v}(\vec{x})$. The difference between these two equations is:
$$
	\vec{e}_{i}\Delta \to \vec{e}_{i}\Delta + (\vec{v}(\vec{x}+\vec{e}_{i}\Delta) - \vec{v}(\vec{x}))\delta t
$$
- Something is happening and I don't really get it. But we end up with:

The volume at some new time $t+\delta t$ is,
$$
	\det\left( \delta ^{a}_{i}\Delta + \frac{ \partial v^{a} }{ \partial x^{i}@ }\Delta\delta t  \right) = \Delta ^{n} \det\left( \delta ^{a}_{i} + \delta t \frac{ \partial v^{a} }{ \partial x^{i} }  \right) = \Delta ^{n} \left( 1+\text{tr}\left( \frac{ \partial v^{a} }{ \partial x^{i} }   \right)\delta t \right)
$$
Which may be further simplified to tell us:
$$
	\Delta ^{n} (1+\vec{\nabla}\cdot \vec{v} \delta t) \implies \frac{d}{dt} \Delta ^{n}(t) \equiv  (\vec{\nabla}\cdot \vec{v}) \Delta ^{n}(t)
$$
Which essentially tells us that the volume of something increases or decreases based on the behaviour of the divergence.

- The Liouville theorem follows as a corollary from this formula
