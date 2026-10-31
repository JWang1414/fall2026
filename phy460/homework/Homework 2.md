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
# Question 3 (Done)
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
# Question 2 (Done)
![[Pasted image 20261029184750.png]]

---
a.
$$
	\begin{align}
	\frac{du}{d\theta} & =v \\
	\frac{dv}{d\theta} & = \alpha-u+\varepsilon u^{2}
	\end{align}
$$
---
b.
Trivially from the first equation:
$$
	v=0
$$
From the quadratic method:
$$
	\varepsilon u^{2}-u+\alpha=0 \implies u= \frac{1\pm \sqrt{ 1-4\alpha\varepsilon }}{2\varepsilon}
$$
There are two points:
$$
	(u, v) = \left( \frac{1+\sqrt{ 1-4\alpha\varepsilon }}{2\varepsilon}, 0 \right), \left( \frac{1-\sqrt{ 1-4\alpha\varepsilon }}{2\varepsilon}, 0 \right)
$$
---
c.
Jacobian matrix:
$$
	\begin{bmatrix}
	0 & 1 \\
	2\varepsilon u-1 & 0
	\end{bmatrix}
$$
Results in the linearized system,
$$
	\begin{bmatrix}
	0 & 1 \\
	\pm \sqrt{ 1-4\alpha\varepsilon } & 0
	\end{bmatrix}
$$
In this case:
$$
	\left( \frac{1-\sqrt{ 1-4\alpha\varepsilon }}{2\varepsilon}, 0 \right) \qquad \begin{bmatrix}
	0 & 1 \\
	-\sqrt{ 1-4\alpha\varepsilon } & 0
	\end{bmatrix}
$$
The eigenvalues are:
$$
	\lambda = \pm i \sqrt[4]{ 1-4\alpha\varepsilon }
$$
Which are purely imaginary. So this is a centre.

I intend to use the following energy functions based on $dv /d\theta$ to show this is a nonlinear centre:
$$
	E = \frac{1}{2} v^{2} + \int \alpha-u + \varepsilon u^{2} \, du = \frac{1}{2}v^{2} + \alpha u - \frac{u^{2}}{2} + \frac{\varepsilon u^{3}}{3}
$$
Which has the gradient:
$$
	\nabla E = \begin{bmatrix}
	\alpha-u+\varepsilon u^{2} \\
	v
	\end{bmatrix}
$$
Which has already been shown to be $\vec{0}$ at the equilibrium points. The behaviour of the extrema at this point is determined by:
$$
	\begin{vmatrix}
	E_{uu} & E_{uv} \\
	E_{vu} & E_{vv}
	\end{vmatrix} = \begin{vmatrix}
	-1+2\varepsilon u & 0 \\
	0 & 1
	\end{vmatrix} = 2\varepsilon u-1
$$
At the equilibrium point:
$$
	2\varepsilon\left( \frac{1-\sqrt{ 1-4\alpha\varepsilon }}{2\varepsilon} \right)-1 = -\sqrt{ 1-4\alpha\varepsilon } \approx -1<0
$$
Since $\varepsilon$ is small. I therefore conclude that this equilibrium corresponds with a local minimum, and so must be a nonlinear centre.

---
d.
The equilibrium necessarily corresponds with a constant $u$, or a constant $r$. If the radius is constant such that $du /d\theta=0$, then this must be a circular orbit.
# Question 4
---
a.
Jacobian matrix:
$$
	\begin{bmatrix}
	0 & 1 \\
	-4 & 0
	\end{bmatrix}
$$
Imaginary eigenvalues, this fixed point is a centre. It is not attracting, but it is Liapunov stable.

For every $\varepsilon$, choose $\delta=\varepsilon /5$. Since this centre is an oval, the furthest some point within $\delta$ may travel is $4\delta=4\varepsilon /5<\varepsilon$. So nearby trajectories are close for all time.

---
b.
$$
	\begin{bmatrix}
	0 & 2 \\
	1 & 0
	\end{bmatrix}
$$
Eigenvalues $\pm \sqrt{ 2 }$. One positive one negative, this is a saddle-point. Neither attracting or Liapunov stable.

---
c.
![[Pasted image 20261029224938.png]]
By observation, this is neither stable nor Liapunov stable.

---
d.
![[Pasted image 20261029225023.png]]
This vector field possess an infinite line of fixed point along the line $y=0$.

It is not stable, because if you choose some fixed point $x^*$, and any arbitrary $\delta$, then you can pick some starting point $x_{0}$ that reaches another fixed point that isn't $x^*$.

It is Liapunov stable. For every $\varepsilon$, choose $\delta=\varepsilon$. All points that begin within $\delta$ will approach the line $y=0$, staying within $\varepsilon$ forever.

---
e.
$$
	\begin{bmatrix}
	-1 & 0 \\
	0 & -5
	\end{bmatrix}
$$
Purely negative eigenvalues. This fixed point is attracting. For all possible values in $\mathbb{R}^{2}$, they will eventually reach (0, 0).

For the same reason, this point is also Liapunov stable. For all $\varepsilon$, choose $\delta=\varepsilon$. All points that start in $\delta=\varepsilon$ will approach the origin, before staying there for all time.

This fixed point is therefore asymptotically stable.

---
f.
$$
	\begin{bmatrix}
	1 & 0 \\
	0 & 1
	\end{bmatrix}
$$
Purely positive eigenvalues. This system is a repelling star. It is neither attracting nor Liapunov stable.

---
![[Pasted image 20261029225736.png]]

In this system there are just two fixed points, $(r, \theta)=(0, 0)$ and $(1, 0)$. The first is unstable, and the second is semi-stable. Therefore, all points in $\mathbb{R}^{2}$ other than (0, 0) will eventually reach (1, 0). I conclude this is an attracting fixed point.

However, for some $\varepsilon$ there will always exist a $\delta$ such that the trajectory will leave the region of $\varepsilon$. For example, if I choose $\varepsilon=1$, and pick the point $(1, \varphi)$ where $\varphi\to 0$ and $\varphi>0$, then the trajectory will loop all the way to $(1, \pi)$ before coming back to (1, 0). Since this point is infinitely close to (1, 0), there is no $\delta$ that will satisfy the definition for Liapunov stable. 

This fixed point is therefore attracting, but not Liapunov stable.
# Question 5 (Done)
![[Pasted image 20261030125530.png]]

---
a.
$$
	r(t) = c_{0}e^{ -t }
$$
At $t=0$ we have,
$$
	r_{0} = c_{0}e^{ 0 } = r_{0}=c_{0} \implies r(t) = r_{0}e^{ -t }
$$
Solve for $\theta$,
$$
	\dot{\theta} = \frac{1}{\ln r} = \frac{1}{\ln(r_{0}e^{ -t })} = \frac{1}{\ln r_{0} -t}
$$
Which has solution,
$$
	\theta(t) = c_{1}-\ln(\ln r_{0}-t)
$$
At $t=0$,
$$
	\theta_{0} = c_{1}-\ln(\ln r_{0}) \implies c_{1}=\theta_{0} + \ln \ln r_{0}
$$
Therefore,
$$
	r(t) = r_{0}e^{ -t } \qquad \theta(t) = \theta_{0} + \ln \ln r_{0} - \ln(\ln r_{0}-t)
$$
---
b.
As $t\to \infty$, $r(t)$ will decay exponentially to 0. That is,
$$
	\lim_{ t \to \infty } r_{0}e^{ -t } =0 \implies \lim_{ t \to \infty } r(t)=0
$$
Furthermore,
$$
	\lim_{ t \to \infty } \left[ \theta_{0} + \ln \ln r_{0} - \ln(\ln r_{0}-t) \right] = \lim_{ t \to \infty } (-\ln(-t)) = \lim_{ t \to \infty } \ln\left( -\frac{1}{t} \right)
$$
This is the same as the limit $\lim_{ x \to 0 }\ln x=-\infty$. I therefore conclude that:
$$
	\lim_{ t \to \infty } \lvert \theta(t) \rvert = \lim_{ t \to \infty } \left\lvert  \ln\left( -\frac{1}{t} \right)  \right\rvert \to \infty
$$
---
c.
Polar to Cartesian coordinates:
$$
	r=\sqrt{ x^{2}+y^{2} } \qquad \theta = \tan ^{-1}\left( \frac{y}{x} \right)
$$
$$
	\dot{r} = \frac{x \dot{x} + y\dot{y}}{r} \qquad \dot{\theta} = \frac{x\dot{y} - y\dot{x}}{r^{2}}
$$
$$
	\dot{r}=-r \qquad \dot{\theta} = \frac{1}{\ln r}
$$
First equation
$$
	\frac{x \dot{x} + y\dot{y}}{r} =-r \implies x \dot{x} + y\dot{y} =-r^{2} = x^{2}+y^{2}
$$
$$
	x \dot{x} + y\dot{y} = x^{2}+y^{2}
$$
Second equation:
$$
	\frac{x\dot{y} - y\dot{x}}{r^{2}} = \frac{1}{\ln r} \implies x\dot{y} - y\dot{x} = \frac{x^{2}+y^{2}}{\ln \sqrt{ x^{2}+y^{2} }}
$$
$$
	x\dot{y} - y\dot{x} = \frac{2(x^{2}+y^{2})}{\ln(x^{2}+y^{2})}
$$
This system of equations has the solution:
$$
	\dot{x} =-x-\frac{2y}{\ln(x^{2}+y^{2})} \qquad \dot{y}=-y+\frac{2x}{\ln(x^{2}+y^{2})}
$$
---
d.
Jacobian matrix:
$$
	\begin{bmatrix}
	\frac{4xy}{(x^{2}+y^{2})\ln ^{2}(x^{2}+y^{2})}-1 & \frac{4y^{2}}{(x^{2}+y^{2})\ln ^{2}(x^{2}+y^{2})} - \frac{2}{\ln(x^{2}+y^{2})} \\
	\frac{2}{\ln(x^{2}+y^{2})} - \frac{4x^{2}}{(x^{2}+y^{2})\ln ^{2}(x^{2}+y^{2})} & -\frac{4xy}{(x^{2}+y^{2})\ln ^{2}(x^{2}+y^{2})} -1
	\end{bmatrix}
$$
Substitute in $x=0$ and $y=0$ to find the linearized system,
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y}
	\end{bmatrix} = \begin{bmatrix}
	-1 & 0 \\
	0 & -1
	\end{bmatrix} \begin{bmatrix}
	x \\
	y
	\end{bmatrix} \implies \begin{cases}
	\dot{x}=-x \\
	\dot{y}=-y
	\end{cases}
$$
Which is a stable star, as needed.

![[Pasted image 20261030163054.png]]

Linearize this system,
$$
	\begin{bmatrix}
	-3x^{2} & -1 \\
	1 & 0
	\end{bmatrix} \implies \begin{bmatrix}
	0 & -1 \\
	1 & 0
	\end{bmatrix}
$$
Where I have substituted in $x=0$ and $y=0$. This has the purely imaginary eigenvalues $\pm i$. So the linear system predicts a centre.

Convert to Polar coordinates,
$$
	r \dot{r} = x \dot{x} + y\dot{y} = x(-y-x^{3}) + y(x)=-x^{4} =-(r\cos\theta)^{4}
$$
$$
	\dot{r} = -r^{3}\cos ^{4}\theta
$$
Now, note that $\cos ^{4}\theta$ is necessarily always positive because of the exponent. Furthermore, $r$ is also an always positive quantity. Therefore,
$$
	\dot{r}=-r^{3}\cos ^{4}\theta <0
$$
Everywhere excluding $r=0$. This implies that the fixed point at the origin must be attracting. So it is actually a stable spiral, as opposed to a centre.
# Question 6 (Done)
![[Pasted image 20261030173013.png]]

---
a.
- $a$ is the birth rate of the rabbits.
- $b$ is the rate at which the foxes hunt the rabbits.
- $c$ is the death rate of the foxes.
- $d$ is the birth rate of the foxes.

The rabbits do not ever die from natural causes. They are exclusively hunted by the foxes. In the same vein, nothing is ever hunting the foxes. They all die from natural causes.

The model assumes an infinite numbers of resources. Even if there are a huge number of rabbits and foxes, somehow, they are all fed.

Rabbit and fox mating could be seasonal.

---
b.
We have,
$$
	\frac{dR}{dt} = aR-bRF \qquad \frac{dF}{dt} = -cF + dRF
$$
Define the new variables:
$$
	F=\frac{a}{b}y \qquad R=\frac{c}{d} x \qquad \tau=at \qquad \mu=\frac{c}{a}
$$
The first equation becomes:
$$
	\begin{align}
	\frac{dR}{dt} & = aR-bRF \\
	 & = aR\left( 1-\frac{b}{a}F \right) \\
	 \frac{c}{d} \frac{dx}{dt} & = \frac{ac}{d} x(1-y) \\
	 \frac{1}{a} \frac{dx}{dt} & = x(1-y) \\
	 x' & = x(1-y)
	\end{align}
$$
Where $x'$ is $dx /d\tau$. Now, the second equation:
$$
	\begin{align}
	\frac{dF}{dt} & = -cF + dRF \\
	 & = cF\left( \frac{d}{c}R-1 \right) \\
	\frac{a}{b} \frac{dy}{dt} & = \frac{ca}{b}y(x-1) \\
	y' & = \frac{c}{a}y(x-1) \\
	 & = \mu y(x-1)
	\end{align}
$$
Where, similarly, $y'=dy /d\tau$. The above yields the system of equations:
$$
	x'=x(1-y) \qquad y'=\mu y(x-1)
$$
---
c.
Add both equations together,
$$
	x'+y' = x(1-y) + \mu y(x-1)
$$
To find a conserved quantity, this must be zero.
$$
	x(1-y) + \mu y(x-1) =0 \implies \frac{1-y}{y} + \mu \frac{x-1}{x} =0
$$
Re-arrange, and integrate both sides,
$$
	\frac{1-y}{y} = \mu \frac{1-x}{x} \implies \int \frac{1-y}{y} \, dy = \mu \int \frac{1-x}{x} \, dx
$$
Evaluate the integrals:
$$
	\ln \lvert y \rvert -y + c_{0} = \mu \left[ \ln \lvert x \rvert -x + c_{1} \right]
$$
Consolidate the integration constant,
$$
	\ln \lvert y \rvert -y= \mu(\ln \lvert x \rvert -x) + c
$$
Which introduces the conserved quantity:
$$
	\mu(x-\ln \lvert x \rvert ) + \ln \lvert y \rvert -y=c
$$
---
d.
Set both equations to zero to find the fixed points:
$$
	x'=x(1-y) =0 \implies x=0, y=1 \qquad y'=\mu y(x-1)=0 \implies x=1, y=0
$$
I conclude that the fixed points are located at $(x, y)=(0, 0)$ and (1, 1). The linearized system is:
$$
	\begin{bmatrix}
	1-y & -x \\
	\mu y & \mu(x-1)
	\end{bmatrix}
$$
Which at the fixed points become:
$$
	A=\begin{bmatrix}
	1 & 0 \\
	0 & -\mu
	\end{bmatrix}_{(0, 0)} \qquad B=\begin{bmatrix}
	0 & -1 \\
	\mu & 0
	\end{bmatrix}_{(1, 1)}
$$
$A$ has purely real eigenvalues, one positive and one negative. $B$ has purely imaginary eigenvalues. So the fixed point at (0, 0) is a saddle, and the fixed point at (1, 1) is a centre.

Notably, the eigenvectors of $A$ are (1, 0) and (0, 1). Therefore, in the first quadrant (with physically plausible conditions) all initial conditions will fall cycles governed by the centre at (1, 1). Only if the initial conditions lie on the $x$ and $y$ axis will there be no cycle.

These two conditions correspond with the case where there are no foxes or there are no rabbits. In the first, the rabbits multiply endlessly, in the second, all the foxes starve.