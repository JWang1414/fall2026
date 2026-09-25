Recall the super and subcritical pitchfork bifurcations:
$$
	\dot{x} = rx-x^{3} \qquad \dot{x} = rx+x^{3}-x^{5}
$$
This form of the subcritical pitchfork looks like:
![[Pasted image 20260925121532.png]]
Furthermore, it is always possible to re-scale some:
$$
	\dot{x} = \tilde{r}x + cx^{3} - dx^{5}
$$
Back to the original version. Simply use $x\to \lambda x$ and $t\to\gamma t$
$$
	\dot{x} = \tilde{r}\gamma x + c\lambda^{2}\gamma x^{3} - d\lambda ^{4}\gamma x^{5}
$$
And then choose $\lambda$ and $\gamma$ so that the 2nd and 3rd terms are both 1.

If we define the potential $\dot{x}=-V(x)$
$$
	V(x) = -\frac{r^{2}}{2}x^{2} + \frac{1}{4}x^{4} - \frac{1}{6} x^{6}
$$
This provides us an equation for the free energy. One we can use to see in what states a system might settle into.

One might, for example, imagine this as the phase of some substance. Initially it might look like a quadratic with "gas" as the minimum. But as the temperature is decreased, two minima will appear. They will eventually become equally likely (degenerate) before the liquid phase dominates the gas phase.

---

We now introduce a new equation, one relevant in cosmology.
$$
	\ddot{x} + 3H\dot{x} =-V'(x)
$$
Where $x$ is the zero mode, a constant part of some scalar. In cosmology, it is a scalar field of "inflation curvatons"

$H=\dot{a} /a$ is called the Hubble parameter.

- This basically says there is a particle moving in a potential, with some friction defined by $3H$.
- In a friction dominated regime people drop the $\ddot{x}$ term

Lets begin by considering a similar equation:
$$
	\epsilon \ddot{x} + \dot{x} + x=0
$$
If you try the substitution $x=e^{ \omega t }x_{0}$ you will get,
$$
	\omega_{\pm} = \frac{-1\pm \sqrt{ 1-4\epsilon }}{\epsilon}
$$
And when $\epsilon\to 0$,
$$
	\omega = -4, -\frac{2}{\epsilon}
$$
Notice that $\omega$ will either be quite small (4) or very very large. That is, large $\omega$ corresponds with a small time scale, and vice versa.

---

Imagine a physical pendulum with length l, position $\theta$, mass $m$, and torque $\Gamma$. The equation of motion for this pendulum is:
$$
	ml^{2} \ddot{\theta} + l \dot{\theta} + mgl\sin\theta = \Gamma
$$
Define the time scale $t=A\tau$ and then use to define the angle:
$$
	\varphi(\tau) = \theta(A\tau)
$$
Where just like $\theta(t)$ it is defined on the region: $\varphi \in(0, 2\pi)$

Note that:
$$
	\begin{align}
	\varphi' & = \dot{\theta} \frac{dt}{d\tau} = \dot{\theta}A \\
	\varphi'' & = \ddot{\theta}A
	\end{align}
$$
Therefore,
$$
	\dot{\theta}=\frac{\varphi'}{A} \qquad \ddot{\theta} = \frac{\varphi''}{A^{2}}
$$
Thus allowing us to re-write the equation of motion as:
$$
	\frac{ml^{2}}{A^{2}}y' + \frac{b}{A}y + mgl\sin \varphi = \Gamma
$$
Where $y(\tau)=\varphi'(\tau)$.
- I have no idea what $b$ is supposed to represent

Choose $A$ so that $\tau$ is dimensionless. So it has units of time. Through dimensional analysis we may define $A$ to be:
$$
	A= \frac{b}{mgl}
$$
Re-arrange for $y'$ to find:
$$
	y'= -\frac{bA}{ml^{2}} \left( y+\frac{mglA}{b} \sin \varphi -\frac{\Gamma A}{b}\right)
$$
And, substituting in $A$:
$$
	y'= -\frac{b^{2}}{m^{2}gl^{3}} \left( y+\sin \varphi -\frac{\Gamma}{mgl} \right)
$$
To clean this up we will also define the dimensionless parameters:
$$
	\frac{1}{\epsilon} = \frac{b^{2}}{m^{2}gl^{3}} \qquad \gamma = \frac{\Gamma}{mgl}
$$
We get the system of equations:
$$
	\begin{align}
	y' & = -\frac{1}{\epsilon} (y+\sin \varphi-\gamma) \\
	\varphi' & = y
	\end{align}
$$
For today we will assume $\gamma=0$.

Also, note that the phase space of this system may be modeled by a cylinder. Since $y\in(-\infty, \infty)$ and $\varphi \in(0, 2\pi)$.

Simple swap of notation:
$$
	\begin{align}
	v_{y} & = -\frac{1}{\epsilon} (y+\sin \varphi) \\
	v_{\varphi} & = y
	\end{align}
$$
Lines in 2D phase space where $v_{1}$ and $v_{2}$ vanish are called nullclines. At the intersection of the nullclines, we find fixed points.

The nullclines for this system is simply $y=0$ and therefore also $-\sin \varphi=0$
- Something about the case where $y$ dominates, and so everything flows onto the nullclines very quickly
- $i\in A$ is short time scale and $A$ is long time scale
- Don't really know what these mean

Now, the fixed points are at $(y, \varphi)=(0, 0)$ and $(0, \pi)$.

Linearizing the fixed points according to:
$$
	x=x_{*} + \delta x(\tau)
$$
Which gives us:
$$
	\begin{align}
	\delta y' & = -\frac{1}{\epsilon}(\delta y + \sin(\varphi_{*}+\delta \varphi)) \\
	\delta \varphi' & = \delta y
	\end{align}
$$
And $\sin(\varphi_{*}+\delta \varphi)$ will collapse to $\delta \varphi$ or $-\delta \varphi$ at fixed points 1 and 2, respectively.
- This can be simplified into matrices form but I didn't write it down in time

---

Generally speaking any differential equation can be written out like:
$$
	\frac{d\vec{x}}{dt}=\vec{Ax}
$$
Also can be written as:
$$
	\frac{dx}{dt} = A\cdot x
$$
Where $x(0)$ is the initial condition.
$$
	x(t) = e^{ At } x(0)
$$
Recall that the exponent to $A$ is:
$$
	e^{ At } = \sum_{n=0}^{\infty} \frac{1}{n!} A^{n}t^{n}
$$
If we can diagonalize $A$:
$$
	A=\begin{bmatrix}
	\lambda_{1} & 0 \\
	0 & \lambda_{2}
	\end{bmatrix} \implies A^{n} = \begin{bmatrix}
	\lambda_{1}^{n} \\
	 & \lambda_{2}^{n}
	\end{bmatrix}
$$
Therefore:
$$
	e^{ At } = \begin{bmatrix}
	e^{ \lambda_{1}t } & 0 \\
	0 & e^{ \lambda_{2}t }
	\end{bmatrix}
$$
A is diagonalizable if the eigenvectors form a basis in $\mathbb{R}^{2}$
$$
	A \begin{bmatrix}
	a_{n} \\
	b_{n}
	\end{bmatrix} = \lambda_{n} \begin{bmatrix}
	a_{n} \\
	b_{n}
	\end{bmatrix}
$$
They form a basis in $\mathbb{R}^{2}$ if any vector can be expressed by:
$$
	\alpha \begin{bmatrix}
	a_{1} \\
	b_{2}
	\end{bmatrix} + \beta \begin{bmatrix}
	a_{2} \\
	b_{2}
	\end{bmatrix}
$$
Where $\alpha$ and $\beta$ are constants.

Using this representation for $x(0)$ the general solution becomes:
$$
	\begin{align}
	x(t) & = e^{ At }x(0) \\
	 & = \alpha e^{ At } \begin{bmatrix}
	 a_{1} \\
	 b_{1}
	 \end{bmatrix} + \beta e^{ At } \begin{bmatrix}
	 a_{2} \\
	 b_{2}
	 \end{bmatrix} \\
	  & = \alpha e^{ \lambda_{1}t } \begin{bmatrix}
	 a_{1} \\
	 b_{1}
	 \end{bmatrix} + \beta e^{ \lambda_{2}t } \begin{bmatrix}
	 a_{2} \\
	 b_{2}
	 \end{bmatrix}
	\end{align}
$$
- Recall that if both eigenvalues are positive than the fixed point is repelling
- If $\lambda_{1}=\lambda_{2}$ (degeneracy) then we have a special repelling point called a "star"
