Let us examine the system of equations:
$$
	\begin{align}
	\dot{x} & =x+e^{ -y } \\
	\dot{y} & = -y
	\end{align}
$$
Using the Taylor series we can linearize this system:
$$
	\begin{align}
	\dot{x} & = x-y \\
	\dot{y} & = -y
	\end{align}
$$
Which yields the matrix representation:
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y}
	\end{bmatrix} = \begin{bmatrix}
	1 & -1 \\
	0 & -1
	\end{bmatrix} \begin{bmatrix}
	x \\
	y
	\end{bmatrix}
$$
You will find that the eigenvalues for this matrix are 1 and -1. The eigenvectors are $[1, 0]$ and $[1, 2]$, respectively.
- Close to some fixed points of interest, this linearized version looks quite similar to the exact solution

Lets define a number of fixed points. I will use the intuitive descriptions
- A fixed point is called *attracting* if a trajectory sufficiently close to it ends at the fixed point
	- The region around this fixed point where this is valid is called the "basin of attraction"
- A fixed point is *Liapunov stable* if all trajectories that start close remain close for all time
	- It is worth noting that neither implies the other
- If something is both Liapunov stable and attracting, then it is called asymptotically stable

If a linearized fixed point is asymptotically stable with $\mathrm{Re}\{ \lambda_{1} \}<0$ and $\mathrm{Re}\{ \lambda_{2} \}<0$ then it is asymptotically stable. If $\mathrm{Re}\{ \lambda_{1} \}>0$ and $\mathrm{Re}\{ \lambda_{2} \}>0$ then it remains unstable.

When we expand from linear to non-linear, generally speaking, the stability does not change, but the nature may vary. A star can change to a saddle, a degenerate node can become a node. Centers may be spirals in reality.

Lets consider an example system. The harmonic oscillator:
$$
	\begin{align}
	\dot{x} & = -y+ax(x^{2}+y^{2}) \\
	\dot{y} & = x+ay(x^{2}+y^{2})
	\end{align}
$$
The linearized version of this is just the harmonic oscillator:
$$
	\begin{bmatrix}
	0 & -1 \\
	1 & 0
	\end{bmatrix}
$$
Which is a centre, as we know.

However, if $a\neq 0$ then it becomes a spiral. $a>0$ is unstable, and $a<0$ is stable.
$$
	\frac{d}{dt}(x^{2}+y^{2}) = 2a(x^{2}+y^{2})^{2} \implies \frac{d}{dt}r^{2} = 2ar^{4}
$$
- This calculation makes it clear how $r$ changes in time depending in the value of $a$.
