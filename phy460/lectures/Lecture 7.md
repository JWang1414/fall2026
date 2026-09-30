Say we have some 2D vector field:
$$
	\dot{x} = v_{x}(x, y) \qquad \dot{y} = v_{y}(x, y)
$$
With a fixed point at $\vec{x}_{*}$

Then this system may be linearized by evaluating:
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y}
	\end{bmatrix} = \begin{bmatrix}
	\frac{ \partial v_{x} }{ \partial x }  & \frac{ \partial v_{x} }{ \partial y }  \\
	\frac{ \partial v_{y} }{ \partial x }  & \frac{ \partial v_{y} }{ \partial y } 
	\end{bmatrix} \begin{bmatrix}
	x \\
	y
	\end{bmatrix}
$$
At the point $\vec{x}_{*}$.

Recall last time that we talked about reducing a 2D vector field to the matrix representation $\dot{x}=Ax$. This matrix may also have the eigenvalues $\lambda_{n}$ with associated eigenvectors $\begin{bmatrix}a_{n} & b_{n}\end{bmatrix}$.

Now, if $\lambda$ are real, and the eigenvectors are not co-linear, then they form a basis on $\mathbb{R}$. That is, any arbitrary vector can be represented as:
$$
	\alpha \begin{bmatrix}
	a_{1} \\
	b_{2}
	\end{bmatrix} + \beta \begin{bmatrix}
	a_{2} \\
	b_{2}
	\end{bmatrix}
$$
We also discussed that, when a matrix is found in the exponential:
$$
	x(t) = e^{ At }x(0)
$$
It may be decomposed into:
$$
	\begin{bmatrix}
	x(t) \\
	y(t)
	\end{bmatrix} = \alpha e^{ \lambda_{1}t } \begin{bmatrix}
	a_{1} \\
	b_{1}
	\end{bmatrix} + \beta e^{ \lambda_{2}t } \begin{bmatrix}
	a_{2} \\
	b_{2}
	\end{bmatrix}
$$
- This is just a linear combination of the two eigenvectors
- Recall that any constant multiple of an eigenvector is also an eigenvector. So eigensolutions form a line

The behaviour of the "flow" on the eigensolutions is dependent on the eigenvalues. For example, when $\lambda_{n}>0$, then we have a repelling fixed point. $\lambda_{n}<0$ corresponds with an attracting fixed point.
- Also called unstable and stable nodes

When $\lambda_{1}=\lambda_{2}$ we have a star. The flow is the same in all directions.

$\lambda_{1}<0$ and $\lambda_{2}>0$ is called a saddle.

So how do we find the eigenvalues? Well, if you recall, the conditions are:
$$
	\det(A-\lambda I)=0 \implies \begin{vmatrix}
	a-\lambda & b \\
	c & d-\lambda
	\end{vmatrix} =0
$$
We can eventually be reduced down to the following algebraic expressions:
$$
	\begin{align}
	(a-\lambda)(d-\lambda)-bc & =0 \\
	\lambda^{2}-\lambda(a+d)+ad-bc & =0 \\
	\lambda^{2}-\lambda \text{trace}(A) + \det(A) & =0
	\end{align}
$$
Which can now be solved with the quadratic equation
1. $(\text{tr}(A))^{2}>4\det(A)$ then we have two distinct eigenvalues
2. $(\text{tr}(A))^{2}=4\det(A)$ then $\lambda_{1}=\lambda_{2}$
	1. If $A$ is symmetric, then $A\propto I$
	2. If $A$ is not symmetric, it has just one eigenvector. This results in what is called a degenerate unstable node
3. $(\text{tr}(A))^{2}<4\det(A)$ then the eigenvalues are complex

If $v$ is complex such that $Av=\lambda v$ then the real and imaginary parts of $v$ are linearly independent in $\mathbb{R}^{2}$ such that:
$$
	x(0) = \alpha \mathrm{Re}\{ v \} + \beta \mathrm{Im}\{ v \}
$$
- Also nice to note that the eigenvectors and eigenvalues are complex conjugates $Av=\lambda v$ and $Av^*=\lambda^*v^*$

This sort of representation allows us to represent $x(t)$ in the form:
$$
	x(t) = e^{ At }x(0) = \left( \frac{\alpha}{2} + \frac{\beta}{2i} \right)e^{ \lambda t } v + \left( \frac{\alpha}{2}-\frac{\beta}{2i} \right) e^{ \lambda^* t } v^*
$$
