Imagine we have $n$ particles in 3D labelled $\vec{r}_{a}$ where $a$ ranges from 1 to $N$. The general force for each particles is labelled such that:
$$
	m_{a}\ddot{\vec{r}}_{a} = \vec{f}_{a} (\vec{r}_{1} \dots\vec{r}_{N}, \dot{\vec{r}}_{1} \dots \dot{\vec{r}}_{N})
$$
This for $\vec{f}_{a}$ could be anything like the Coulomb or Newton equations.

This is an example of a non-linear system. One we have largely no hope of solving analytically.

Let use the pendulum equation as an example here:
$$
	\ddot{\theta} = -\omega^{2}(t) \sin\theta \qquad \text{where } \omega=\sqrt{ \frac{g}{l} }
$$
We can apply the general linearization method where we use $x_{1}=\theta$ and $x_{2}=\dot{\theta}$
$$
	\dot{x}_{1} = x_{1} \qquad \dot{x}_{2} =-\omega^{2}(t)\sin x_{1}
$$
And to remove the explicit time dependence define $x_{3}=t$,
$$
	\dot{x}_{1}=x_{2} \qquad \dot{x}_{2}=-\omega^{2}(x_{3})\sin x_{1} \qquad \dot{x}_{3}=1
$$
So now we have a time-independent system of equations.

So how might this look like if we instead had equations on $\mathbb{R}^{n}$
$$
	\dot{x}_{1} = v_{1}(x_{1}\dots x_{n}) \qquad \dots \qquad \dot{x}_{n} = v_{n}(x_{1}\dots x_{n})
$$
Which has $n$ equations with no explicit $t$-dependence.

Lets now introduce vector fields. Where we are attempting to solve the equation:
$$
	\dot{\vec{x}} = \vec{v}(\vec{x})
$$
Which is defined on $\mathbb{R}^{n}$.

When we say we are trying to find the trajectory in $\mathbb{R}^{n}$ we are essentially saying that with:
$$
	\vec{x}(0) = \vec{x}_{0}
$$
We would like to know $\vec{x}(t)$ for all $t$.
- This is just initial conditions and a solution

One possible interpretation is, in a 3D space, we have the vector field $\vec{v}(\vec{x})$ and we would like to find $\vec{x}(t)$ where it is tangential everywhere to the vector field.

$\vec{x}(t)$ is called the trajectory, $\dot{\vec{x}}(t)$ is the velocity. $\vec{v}(\vec{x})$ is the actual vector field, and the integral of $\vec{v}(\vec{x})$ is roughly the flow of the particles.

Lets look at a few examples of flows to get an idea of what we're looking at here.

One common example of a flow is a boring one. One that is continuous and flows forward. Zooming in will reveal a bunch of parallel arrows. In this case we may roughly claim that $\vec{v}(\vec{x})\approx \vec{v}_{0}$.

So now when we try to solve our equation for the trajectory $\dot{x}=\vec{v}_{9}\vec{x}$
$$
	\frac{d}{dt}(\vec{x}-\vec{x}_{0}) \approx \vec{v}_{0} = \text{const.} \implies \vec{x} = \vec{x}_{0} + \vec{v}_{0}t
$$
Which works just fine for small $t$.

A slightly less boring example might be an infinite sink. So all the arrows are converging onto one point. At the centre of this sink, is a fixed point, where the vector field vanishes. That is $\vec{v}(\vec{x})=0$. It is called a fixed point because when $\vec{v}(\vec{x})=0$, then $\vec{x}$ is constant.
- A sink is also an example of an attractive fixed point

For now, however, we will try to limit our analysis to one dimensional flows. In this case our equation flattens into the 1D version $\dot{x}=v(x)$. (Notice the dropped arrows).

Our first example is:
$$
	v(x) = \sin x
$$
It is up to us to decide whether or not $x$ is dependent on time here. Or perhaps because $\sin x$ is a periodic function, then it is dependent on time in the form of its periodic points. For the time being, we will just say this is some line on $\mathbb{R}$. Now, at all points when $\sin x=0$, we have a fixed point. With both attracting (stable) and repelling (unstable) fixed points.