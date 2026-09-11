Going back to the Lipshitz condition, we know that if the condition is valid on some region, then uniqueness applies.

Now, lets begin with the leaky bucket problem.

We have a bucket. It has a small hole in the bottom. It has area $A$, height $h$, and $\epsilon$ is the area of the hole.

Assume that $A\gg\epsilon$. Now, the draining of the water will cause some change in the water's height inside the bucket $\Delta h$.

The potential energy in this layer $\Delta h$ at $h$ is:
$$
	mgh = (\Delta hA\rho)gh
$$
Where $\rho$ is the mass density.

The volume of the water flowing out of the bucket is:
$$
	\Delta t v\epsilon
$$
Where $\Delta t$ is the change in time, and $v$ is the velocity (assumed constant)

This volume must be conserved:
$$
	\Delta hA = \Delta tv\epsilon \implies \frac{\Delta h}{\Delta t} = \frac{\epsilon}{A}v
$$
The kinetic energy of the outflow is:
$$
	\frac{1}{2}mv^{2} = \frac{1}{2} (\Delta tv\epsilon \rho)v^{2} = (\Delta hA\rho)gh
$$
Which has been equated to the previously determined change in potential energy.

From volume conservation, the right side can be simplified to:
$$
	(\Delta hA\rho)gh = \Delta tv\epsilon \rho gh
$$
So now we can simplify the equation we have already found into:
$$
	\frac{v^{2}}{2} = gh \implies v=\sqrt{ 2gh }
$$
Furthermore the change in height over time will be:
$$
	\frac{\Delta h}{\Delta t} = \frac{\epsilon}{A}v \implies \frac{dh}{dt} = \frac{\epsilon}{A} \sqrt{ 2gh } \propto  \sqrt{ h }
$$
So we have learned in this system that:
$$
	v=\sqrt{ 2gh } \qquad \frac{dh}{dt} = \frac{\sqrt{ 2g }\epsilon}{A}\sqrt{ h }
$$
Now, for convenience, let us define:
$$
	\frac{dh}{dt} = -2c\sqrt{ h } \implies \frac{dh}{\sqrt{ h }} = -2c \, dt
$$
Which, since the derivative for the square root is:
$$
	d\sqrt{ x } = \frac{dx}{2\sqrt{ x }}
$$
This can be simplified into:
$$
	2d\sqrt{ x }=-2c \, dt
$$
Which is a differential equation we can solve, yielding:
$$
	h(t) = (\sqrt{ h_{0} }-C(t-t_{0}))^{2}
$$
And the time to reach $h=0$ is:
$$
	\sqrt{ h_{0} }-C(t-t_{0})=0 \implies t-t_{0} = \frac{\sqrt{ h_{0} }}{C}
$$
Which is a finite amount of time.

At its simplest, this equation resembles the function $h(t)=(Ct)^{2}$. Since $t>0$, when graphed this because a plot that begins at zero and goes up quadratically. Notice, then, that it will constantly stay at 0 afterwards. So, this is not unique. If the bucket is empty, we cannot learn anything about how much time has passed.

---

Lets now analyze the logistic equation. To begin, we will look at the population equation:
$$
	\frac{dN}{dt} = rN \implies N(t) = N_{0} e^{ rt }
$$
One might also imagine the "explosion equation" which is instead:
$$
	\frac{dN}{dt} = rN^{2}
$$
Solving the equivalent equation $\dot{x}=x^{2}$ yields:
$$
	x(t) = \frac{1}{x_{0}^{-1}-t}
$$
Notice that this equation blows up in a finite amount of time.
- It explodes, as advertised

Now, another population equation is:
$$
	\frac{dN}{dt} = rN\left( 1-\frac{N}{K} \right)
$$
Which, if you notice, places a fixed point at $N=K$. This point $K$ is called the carrying capacity. In fact, this fixed point is attracting
- This is a problem in our homework
