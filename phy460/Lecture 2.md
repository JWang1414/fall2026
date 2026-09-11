Recall from the previous class we covered some content related to 1D flows. Where the equation for the trajectory is $\dot{x}=v(x)$. The fixed points are located where $v(x)=0$.
- Classifications of 1D fixed points are: attracting, repelling, and semi-stable
- A linearized analysis can be done for attracting and repelling fixed points, but not for semi-stable points. This is just because semi-stable points result from quadratic $v(x)$. So you don't get any useful information

To linearize we use:
$$
	f(x) \approx f(x_{0}) + f'(x_{0}) (x-x_{0})
$$
Where $f(x_{0})=0$ since we are at a fixed point.

Which results in the differential equation:
$$
	\dot{x} = v(x) \approx f(x) \implies \dot{x} = (x-x_{0})f'(x_{0})
$$
The solution to this is:
$$
	x(t) - x_{0} = (x(0)-x_{0}) e^{ f'(x_{0})t }
$$
So in the case where $f'(x)>0$, the trajectory is leaving, and vice versa. This corresponds with repelling and attracting fixed points.

As a reminder for uniqueness theorems for 1D, we will define some conditions.

$$
	\dot{x}=v(x) \qquad x \in \mathbb{R}
$$
Will be referred to as [E].

$v(x)$ is called smooth for some interval if it is continuous and once differentiable. And a smooth function obeys the Lipshitz condition if:
$$
	\lvert \vec{v}(x) - \vec{v}(y) \rvert < k\lvert \vec{x}-\vec{y} \rvert
$$
For some constant $k>0$. This can also be re-arranged to the more suggestive form:
$$
	\frac{\lvert v(x)-v(y) \rvert }{\lvert x-y \rvert }<k
$$
Which will be referred to as [L].

Note that [L] implies continuity and a non-zero derivative.

If the function is smooth, and [E], then the solution is unique on the interval. This also necessarily means that [E] and [L] would mean the solution is unique.

Lets now look at a physical condition about uniqueness. Suppose $v(x_{0})=0$, so $x_{0}$ is a fixed point. Now, if this fixed point is attracting, and we begin at some point $x\neq x_{0}$, does it take a finite or infinite amount of time to reach $x_{0}$? If it is finite, then the solution isn't unique. If it is infinite, then it is unique.

Lets investigate this non-uniqueness and finite-ness of time in more detail. Say we have some time to fall defined like:
$$
	\Delta t = \int_{x}^{x_{0}} \frac{1}{v(x')} \, dx'
$$
Say our function is $\alpha \lvert x-x_{0} \rvert^{\beta}$. Which satisfies our condition that $v(x_{0})=0$.

Computing this integral...
$$
	\Delta t = \int_{x}^{x_{0}} \frac{1}{\alpha \lvert x'-x_{0} \rvert ^{\beta} } \, dx' = \int \frac{1}{x^{\beta}} \, dx \propto  x^{1-\beta}
$$
In particular, notice that when $\beta<1$, $x\to 0$ is finite. And if $\beta>1$ then $x\to 0$ is infinite.