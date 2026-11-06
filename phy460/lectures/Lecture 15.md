Recall that last session we introduced the equation:
$$
	\ddot{x} + \alpha \dot{x} + \sin x = \Gamma
$$
Which can be expressed as the system of equations:
$$
	\begin{align}
	\dot{x} & =y \\
	\dot{y} & = \Gamma - \sin x - \alpha y
	\end{align}
$$
Note that the phase plane is a periodic cylinder with $x \in[-\pi, \pi]$ and $y\in \mathbb{R}$.

The nullclines of this system occur when,
$$
	y=0 \qquad y= \frac{1}{\alpha}(\Gamma-\sin x)
$$
The factor of $\Gamma$ will move the sine function up and down on the cylinder. So, in the case when $\lvert \Gamma \rvert>0$, the function will no longer intersect with the $y=0$ nullcline, removing the fixed points.
- These two fixed points will be either a stable node/spiral and a saddle node
- Specifically, when $\alpha^{2}>4(1-\Gamma^{2})$ it is a stable node, otherwise it is a spiral
- Recall that system is modelling a pendulum. This is basically just saying that when the friction is large enough, the pendulum won't swing, otherwise, it will slowly decay
- Generally speaking, when $\lvert \Gamma \rvert<1$, we will end up at a fixed point

In the case where $\lvert \Gamma \rvert>1$, we actually end up with a limit cycle. To study this limit cycle, and prove that one exists, we must begin by discussing another theorem/topic.

First we introduce the Poincare map, which is any map from $[y_{1}, y_{2}]\to[y_{1}, y_{2}]$.
- In our case, let $y$ be the position at $x=-\pi$. We define the Poincare map $P(y)$ be the position at $x=-\pi$
- What does $P(y)$ actually describe? Well, this is just what happens after one period. So $P(y)$ tells us what happens to $y$ after evolving in the system for one discrete period

Now, if $P(y_{*})=y_{*}$ is a fixed point of the Poincare map, then it is a closed trajectory, or limit cycle.
- Note, we cannot use index theory here, because the space is periodic, it is not contractible.

So, to prove that there is a limit cycle, we would like to show:
1. $\exists y_{*}$ such that $P(y_{*})=y_{*}$ (so it is a fixed point)
2. Show that $y_{*}$ is unique

Note that $y_{1}$ is the lower boundary on the map space, and $y_{2}$ is the upper bound. In our case, we have the following properties with $P(y)$:
1. $P(y_{1})>y_{1}$. So points that begin on the lower bound tend to increase
2. $P(y_{2})<y_{2}$. So points that begin on the upper bound tend to decrease
3. $P(y)$ is a continuous function of $y$
4. $P(y)$ is monotonically increasing

Based on these qualities, we can see that $P(y)$ must cross the diagonal somewhere on the map $[y_{1}, y_{2}]$. Therefore, there must be some case where $y_{*}$ maps to itself, and so a fixed point must exist.

- The uniqueness proof is a pretty classic one. You assume there are two limit cycles, and then assume they are the same. You arrive at a contradiction, so the two limit cycles must be unique from each other

Define the energy function:
$$
	E(y, x) = \frac{1}{2}y^{2} - \cos x
$$
$E(y, x)$ must be constant after some period such that:
$$
	\Delta E = \int_{-\pi}^{\pi} \frac{dE}{dx} \, dx =0
$$
Solve for $dE /dx$,
$$
	\frac{dE}{dx} = \frac{ \partial E }{ \partial x } \frac{ \partial y }{ \partial x } + \frac{ \partial E }{ \partial x } = y \frac{dy}{dx} + \sin x = d \frac{dx /dt}{dx /dt} + \sin x = y \frac{\Gamma-\alpha y-\sin x}{y} + \sin x
$$
$$
	\frac{dE}{dx} = \Gamma- \alpha y
$$
Which therefore gives us:
$$
	\int_{-\pi}^{\pi} \Gamma-\alpha y \, dx = 2\pi\Gamma + \alpha \int_{-\pi}^{\pi} y(x) \, dx  =0 \implies \int_{-\pi}^{\pi} y(x) \, dx = \frac{2\pi\Gamma}{\alpha}
$$
