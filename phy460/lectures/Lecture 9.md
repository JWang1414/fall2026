Recall that near the fixed points we may linearize the system:
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y}
	\end{bmatrix} = A \begin{bmatrix}
	x \\
	y
	\end{bmatrix}
$$
By adjusting the matrix so that it is:
$$
	A= \begin{bmatrix}
	\frac{ \partial v_{x} }{ \partial x }  & \frac{ \partial v_{x} }{ \partial y }  \\
	\frac{ \partial v_{y} }{ \partial x }  & \frac{ \partial v_{y} }{ \partial y }
	\end{bmatrix}
$$
- Which kind of resembles a Jacobian.

We have already looked at/classified saddles, nodes, degenerate nodes, stars, centres, and spirals.

Last time we began looking at limit cycles. It's basically a fully enclosed circle in the vector field.
- Stuff might be attracted to or repelled by this circle
- Stuff will go around indefinitely
# Index Theory
Say we have some 2D vector field $\vec{v}$. Where we define $x=v_{x}$ and $y=v_{y}$.

Now define some closed loop $C$ such that $\vec{v}\neq 0$ on $C$. See that the normal vector $\vec{n}=\vec{v} /\lvert \vec{v} \rvert$ is defined for all points in $C$.

The index of $\vec{v}$ along $C$ is the number of counter-clockwise rotations $\vec{n}$ makes as you go around $C$ counter-clockwise.
- More complicated loops are allowed, but it is okay to just consider simple loops
- The loop $C$ is deformable into some topologically equivalent $S^{1}$

- It is possible to draw an index map from $S^{1}$ in $xy$-space to $S^{1}$ in $\vec{n}$-space. This is basically a way to visualize the winding numbers
	- I don't have a good diagram for this
	- It is a trivial map from circle to circle

The index of the star, for example, is 1. We say $I(\text{star})=1$
- $I(\text{saddle})=-1$ (because it goes clockwise)
- All linearized nodes like stars and degenerate nodes have index 1

The index has a number of properties.
1. The index number across some loop $C$, assuming no fixed points are crossed, is a topological invariant (doesn't change upon deforming $C$)
2. The index number that encloses several fixed points is the sum of the index number of each fixed point inside
	1. Kind of like a quantum number. The index number basically abides by superposition
