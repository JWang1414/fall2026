Last time, while discussing the search for eigenvalues, we covered the case where there are real eigenvalues.

Thus, we move onto the case where there are imaginary eigenvalues.

The eigenvalues will be complex conjugates with each other:
$$
	Av=\lambda v \qquad Av^* = \lambda^*v
$$
Where $A$ is a real 2x2 matrix. and $v=\begin{bmatrix}v_{1} & v_{2}\end{bmatrix}\in \mathbb{C}^{2}$.

We claim that $\mathrm{Re}v$ and $\mathrm{Im}v$ are linearly independent on $\mathbb{R}^{2}$ and so form a basis for $\mathbb{R}^{2}$.

This necessarily means that any initial condition $x(0)$ can be expressed as a linear combination of these two parts:
$$
	x(0) = \alpha v'+  \beta v''
$$
Where $v'=\mathrm{Re}v$ and $v''=\mathrm{Im}v$.

Now, the expression for $\dot{x}(t)$ is:
$$
	\dot{x}(t) = Ax(t) \implies x(t) = e^{ At }x(0)
$$
Substituting in our expression for the initial conditions:
$$
	= e^{ At }(\alpha v'+\beta v'')
$$
And using this identity for the real and complex parts:
$$
	v'=\frac{v+v^*}{2} \qquad v''=\frac{v-v^*}{2i}
$$
Our expression becomes:
$$
	x(t) = \frac{1}{2} \left( \alpha+\frac{\beta}{i} \right) e^{ \lambda t }v + \frac{1}{2}\left( \alpha-\frac{\beta}{i} \right)e^{ \lambda^*t }v^*
$$
Notice, that using the same identity, this can be further reduced into:
$$
	\mathrm{Re}\left\{  \left( \alpha+\frac{\beta}{i} \right) e^{ \lambda t }v  \right\}
$$
Where recall that $\lambda$ and $v$ are both also complex. We find that...
$$
	= e^{ \lambda't } \mathrm{Re}\left\{  \left( \alpha+\frac{\beta}{i} \right) e^{ i\lambda''t } (v'+iv'')  \right\}
$$
This function is either increasing or decreasing based on the value of $\lambda'$. Telling us that the stability is determined by the value of $\lambda'$. The real part of $\lambda$.
- Positive means unstable, and negative means stable

Evaluating this further yields the representation:
$$
	= e^{ \lambda't } \alpha(\cos (\lambda''t)v'-\sin(\lambda''t)v'') + e^{ \lambda't } \beta(\sin(\lambda''t)v' + \cos(\lambda''t)v'')
$$
Notice that the complex part $\lambda''$ defines some oscillatory behaviour. The complex part of the eigenvalues is essentially what's responsible for "spirals" appeared in 2D phase portraits.
- When you have a non-zero real part and a complex part, you have a *spiral*
- When the real part is zero, but a non-zero complex part, you have a *centre*

Going back to our pendulum with length $l$, mass $m$, gravity $g$, and some force of friction, recall that the system of equations we found was:
$$
	\dot{\phi}=y \qquad y' = -\frac{1}{\epsilon} (y+\sin \phi)
$$
- $\epsilon$ small corresponds with large friction and vice versa

We may now use our new tools to analyze the matrix representation for this system:
$$
	\begin{bmatrix}
	\phi \\
	y
	\end{bmatrix}' = \begin{bmatrix}
	0 & 1 \\
	-1 /\epsilon & -1 /\epsilon
	\end{bmatrix} \begin{bmatrix}
	\phi \\
	y
	\end{bmatrix}
$$
Analyze the trace and determinant:
$$
	(\text{tr}A)^{2} - 4\det A = \frac{1}{\epsilon^{2}} - \frac{4}{\epsilon}
$$
When $\epsilon$ small we have real eigenvalues, and when $\epsilon$ is large we have complex eigenvalues.
- Small is large friction, so the pendulum quickly falls to the fixed point
- Large is small friction, so the pendulum is oscillating
