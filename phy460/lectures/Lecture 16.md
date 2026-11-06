We will begin our study of the Lorenz equations and chaos by introducing some concepts with convection rolls.

Say we have some $\dot{x}_{i}=v_{i}(x)$ where $i=1\dots n$. This can be imagined as some volume in $v_{1}\dots v_{n}$ space, which necessarily has the divergence,
$$
	\sum_{i=1}^{N} \frac{ \partial  }{ \partial x_{i} } = \vec{\nabla}\cdot \vec{v}
$$
From the Liouville theorem, we have that:
$$
	\begin{align}
	\vec{\nabla}\cdot \vec{v}=0 & \iff \text{volume is preserved} \\
	\vec{\nabla}\cdot \vec{v}>0 & \iff \text{volume increases} \\
	\vec{\nabla}\cdot \vec{v}<0 & \iff \text{volume decreases}
	\end{align}
$$
This last case (the 3rd) is the regime where strange attractors occur.

To study a model of convection rolls, we will use the chaotic waterwhell described by Steven Strogatz. It has the parameters: inflow rate $Q(\theta)$, radius $r$, leak rate $K$, rotational damping rate $\nu$.

The mass between $\theta$ and $\theta+d\theta$ for all time will be called $m(\theta, t) \, d\theta$, and the angular velocity is $\omega(t)$.

Assume that we have an in-compressible, constant volume fluid, and torque balance.

The mass between two points $\theta_{1}$ and $\theta_{2}$ is:
$$
	M = \int_{\theta_{1}}^{\theta_{2}} m(\theta, t) \, d\theta
$$
To compute the change in $M$ over some time $\Delta t$ we must collect contributions from the inflow, draining, and rotation of the wheel:
$$
	\Delta t \int_{\theta_{1}}^{\theta_{2}} Q(\theta) \, d\theta \qquad - \Delta t\int_{\theta_{1}}^{\theta_{2}} Km(\theta, t) \, d\theta \qquad -\omega\Delta t \left[ m(\theta_{2}, t)  - m(\theta_{1}, t)\right]
$$
Accounting for all of these, the total change can be re-written as:
$$
	\Delta M = \Delta t \left[ \int_{\theta_{1}}^{\theta_{2}} Q(\theta) \, d\theta - K \int_{\theta_{1}}^{\theta_{2}} m(\theta, t) \, d\theta - \omega \int_{\theta_{1}}^{\theta_{2}} \frac{ \partial m(\theta, t) }{ \partial \theta }  \, d\theta  \right]
$$
From which we derive a continuity equation":
$$
	\frac{ \partial m(\theta, t) }{ \partial t } = Q(\theta) - Km(\theta, t) - \omega \frac{ \partial m(\theta, t) }{ \partial \theta }
$$
Alright, now lets tackle the torque balance. Define $I$ as the moment of inertia, which will will say is constant. Why?
1. Constant $I$ is actually approached exponentially in time
2. Assume $I_\text{water}\ll I_\text{metal}$

The functional torque (the object rotating around the axis) is:
$$
	I\dot{\omega} = -\nu \omega
$$
Define $\alpha$ as the angle between the water wheel and the table it is resting on. The gravitational torque is:
$$
	d\tau = gr \sin\theta m(\theta, t) \, d\theta
$$
Where $g\to g\sin\alpha$. Just to simplify the notation. Combining these two:
$$
	\dot{I}\omega = -\nu \omega + gr \int_{0}^{2\pi} \sin\theta m(\theta, t) \, d\nu
$$
Recall that $Q(\theta)$ is given, since we control it. Lets say that $Q(\theta)$ is an even function.

Express $Q(\theta)$ and $m(\theta, t)$ as their Fourier transforms:
$$
	\begin{align}
	Q(\theta) & = \sum_{n\geq 0} q_{n}\cos(n\theta) \\
	m(\theta, t) & = \sum_{n\geq 0} a_{n}(t)\sin(n\theta) + b_{n}(t) \cos(n\theta)
	\end{align}
$$
Where $q_{n}$ is some constant.

Substituting these into the continuity equation we derived. We find that:
$$
	\begin{align}
	\dot{a}_{n} & = -Ka_{1} +  n\omega b_{n} \\
	\dot{b}_{n} & = q_{n}-Kb_{n} - n\omega a_{n}
	\end{align}
$$
Doing the same for the torque we get:
$$
	I\dot{\omega}=-\nu \omega + \pi gra_{1}
$$
Since just the first Fourier coefficient survives.
- These equations can then be used to solve for each coefficient, and predict how the system might behave

So what are the fixed points? Well, we can find one of them at:
$$
	\omega^{2}+K^{2} = \frac{\pi grq_{1}}{\nu}
$$
This models the simple cases with the water wheel rotating.
- Not sure what type of rotation. But we are not interested in this one

For the next section, we will compare the equations we have obtained with the Lorenz equations:
$$
	\begin{align}
	\dot{x} & = \sigma(y-x) \\
	\dot{y} & = rx-xz-y \\
	\dot{z} & = xy-bz
	\end{align}
$$
