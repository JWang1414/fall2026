# Question 1 (Not done)
---
1.
Determine the value of $A^{n}$:
$$
	A^{n} = \begin{bmatrix}
	\lambda ^{n} & cn\lambda ^{n-1} \\
	0 & \lambda ^{n}
	\end{bmatrix}
$$
$e^{ At }$ is therefore:
$$
	e^{ At } = \sum_{n=0}^{\infty} \frac{t^{n}}{n!} \begin{bmatrix}
	\lambda ^{n} & cn\lambda ^{n-1} \\
	0 & \lambda ^{n}
	\end{bmatrix} = \begin{bmatrix}
	C & D \\
	E & G
	\end{bmatrix}
$$
Trivially, $E=0$. Additionally,
$$
	C=G= \sum_{n=0}^{\infty} \frac{t^{n}\lambda ^{n}}{n!} = e^{ \lambda t }
$$
Now solve for $D$,
$$
	D = \sum_{n=0}^{\infty} \frac{t^{n}(cn\lambda ^{n-1})}{n!} = \sum_{n=0}^{\infty} c \frac{t^{n}\lambda ^{n-1}}{(n-1)!} = ct \sum_{n=0}^{\infty} \frac{t^{n-1}\lambda ^{n-1}}{(n-1)!} = ct e^{ \lambda t }
$$
Therefore I conclude that,
$$
	e^{ At } = e^{ \lambda t } \begin{bmatrix}
	1 & ct \\
	0 & 1
	\end{bmatrix}
$$
Verify,
$$
	\frac{d}{dt} e^{ At } = \frac{d}{dt} \begin{bmatrix}
	e^{ \lambda t } & cte^{ \lambda t } \\
	0 & e^{ \lambda t }
	\end{bmatrix} = \begin{bmatrix}
	\lambda e^{ \lambda t } & c e^{ \lambda t }(\lambda t+1) \\
	0 & \lambda e^{ \lambda t }
	\end{bmatrix} = e^{ \lambda t } \begin{bmatrix}
	\lambda & c(\lambda t+1) \\
	0 & \lambda
	\end{bmatrix}
$$
$$
	Ae^{ At } = \begin{bmatrix}
	\lambda & c \\
	0 & \lambda
	\end{bmatrix} \begin{bmatrix}
	e^{ \lambda t } & ct e^{ \lambda t } \\
	0 & e^{ \lambda t }
	\end{bmatrix} = \begin{bmatrix}
	\lambda e^{ \lambda t } & c e^{ \lambda t } + c\lambda t e^{ \lambda t } \\
	0 & \lambda e^{ \lambda t }
	\end{bmatrix} = e^{ \lambda t } \begin{bmatrix}
	\lambda & c(\lambda t+1) \\
	0 & \lambda
	\end{bmatrix}
$$
So $\frac{d}{dt}e^{ At }=Ae^{ At }$ as needed.

---
2.
$$
	\begin{bmatrix}
	x(t) \\
	y(t)
	\end{bmatrix} = e^{ At } \begin{bmatrix}
	x_{0} \\
	y_{0}
	\end{bmatrix} = e^{ \lambda t } \begin{bmatrix}
	1 & ct \\
	0 & 1
	\end{bmatrix} \begin{bmatrix}
	x_{0} \\
	y_{0}
	\end{bmatrix} = e^{ \lambda t } \begin{bmatrix}
	x_{0}+cy_{0}t \\
	y_{0}
	\end{bmatrix}
$$
- For $\lambda=2$ and $c=3$, it is originally a repelling star. But as $t\to \infty$ it appears to reduce to an unstable degenerate node
- For $\lambda=2$ and $c=-3$, the case is the same as above. But the direction has swapped
- For $\lambda=-2$ and $c=2$, the behaviour is the same, but the strength of the vector field decays quickly as we move away from $(x, y)=(0, 0)$
---
3.
This is a degenerate node with just one eigenvalue $\lambda$ and eigenvector $[1, 0]$. By observation, the index of the vector field should be 1.

---
4.
$$
	I_{C} = \frac{1}{2\pi} \oint_{C} \frac{f \, dg - g \, df}{f^{2}+g^{2}}
$$
Where $\dot{x}=f(x, y)$ and $\dot{y}=g(x, y)$ along some curve $C$
- Continue this question later

---
5.
A degenerate node forms at (0, 0) because $A$ has just a single eigenvalue $\lambda$. 

Linear form:
$$
	\begin{align}
	\dot{x} & = \lambda x+cy \\
	\dot{y} & = \lambda y
	\end{align}
$$
One example of a non-linear modification might be:
$$
	\begin{align}
	\dot{x} & = \lambda x+cy \\
	\dot{y} & = \lambda y + y^{3}
	\end{align}
$$
Which would have the linearized system:
$$
	\begin{bmatrix}
	\lambda & c \\
	0 & \lambda+3y^{2}
	\end{bmatrix} \implies \begin{bmatrix}
	\lambda & c \\
	0 & \lambda
	\end{bmatrix}
$$
Dropping the quadratic terms to maintain a linear system. Note that, on the contrary, the actual system,
$$
	\begin{bmatrix}
	\lambda & c \\
	0 & \lambda+y^{2}
	\end{bmatrix} \begin{bmatrix}
	x \\
	y
	\end{bmatrix}
$$
Has two eigenvalues $\lambda$ and $\lambda+y^{2}$, with two different eigenvectors.
- I have no idea if this is right. I feel like it's wrong
# Question 2 (Done)
![[Pasted image 20261028205045.png]]
a.
$-k\theta$ is linear and therefore has no unique value on the circle. A well-defined vector field doesn't exist on the circle, so this problem should be visualized on the line.

---
b.
Divide by $mgL$
$$
	\frac{bL}{mg} \dot{\theta} + \sin\theta = \frac{\Gamma-k\theta}{mgL} = \frac{d\theta}{d\tau} + \sin\theta = \gamma - \kappa\theta
$$
Where I have defined:
$$
	\tau = \frac{mg}{bL}t \qquad \gamma=\frac{\Gamma}{mgL} \qquad \kappa = \frac{k}{mgL}
$$
The final equation is:
$$
	\frac{d\theta}{d\tau} = \gamma-\sin\theta - \kappa\theta
$$
---
c.
The fixed points will be determined by:
$$
	\gamma-\sin\theta - \kappa\theta =0
$$
In the case when $\kappa<0$, the spring will force the pendulum further as the spring winds up, and pulls the pendulum as the spring winds down. Depending on the starting position $\theta(0)$, generally speaking, the pendulum will wrap around forever. There will, however, be some stable fixed points.

In the case where $\kappa=0$, this returns to the original over-damped pendulum case. The pendulum will either settle at a fixed point, or it will oscillator forever.

In the physical case, which is when $\kappa>0$, as the pendulum is forced forwards such that $\theta$ increases, the spring will wind up and pull it back. Because of this, the pendulum will eventually settle at some stable fixed point, where the spring and driving force balance.

---
d.
![[Pasted image 20261028212207.png]]
A plot of $\gamma-\sin\theta-\kappa\theta$ with $\gamma=1$ and $\kappa=0.1$. See that there are a myriad of stable and unstable fixed points here.

![[Pasted image 20261028212355.png]]
$\kappa=0.2$. As the value of $\kappa$ is increased, the number of fixed points (in this case) will decrease.

From this example, it is possible to tell that these bifurcations are saddle-node bifurcations. Stable and unstable nodes appear in pairs before annihilating each other.
# Question 3
