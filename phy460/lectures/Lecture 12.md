Recall that duck vs dog problem. The duck is confined to a circle with radius $r$ such that:
- The $\vec{x}$ here is supposed to be $\vec{X}$
$$
	\lvert \vec{x} \rvert = \omega r=v=\text{const.}
$$
The dog begins at some arbitrary position $\vec{\rho}$, and its position changes like:
$$
	\lvert \dot{\vec{p}} \rvert = u = \text{const.}
$$
The dog is always moving towards the duck. The vector between the two can be written as $\vec{R}=\vec{x}-\vec{\rho}$.

The movement of the dog is therefore:
$$
	\dot{\vec{\rho}}= u \frac{\vec{R}}{\lvert R \rvert }= u \frac{\vec{x}-\vec{\rho}}{\lvert \vec{x}-\vec{\rho} \rvert }
$$
Call the angle between $\vec{x}$ (position of the duck) and $\vec{R}$ (direction the dog is moving) as $\phi$.

Our current goal is to manipulate the problem into a nicer form.
$$
	\dot{\vec{X}}\cdot \vec{R} = \omega rR \sin \phi \qquad \vec{X}\cdot \vec{R} = rR \cos \phi
$$
Furthermore, using the chain rule and these two representations,
$$
	\frac{d}{dt} (\vec{X}\cdot \vec{R}) = \dot{\vec{X}}\cdot \vec{R} = \vec{X}\cdot \dot{\vec{R}} = \omega rR\sin \phi + \vec{X}\cdot \dot{\vec{R}}
$$
$$
	\frac{d}{dt} (\vec{X}\cdot \vec{R}) = r\dot{R} \cos \phi - rR \dot{\phi} \sin \phi
$$
After a complicated series of calculations I was not able to write down, you get:
$$
	\dot{R} = \omega r\sin \phi - u
$$
$$
	-r\dot{R}\cos \phi + rR(\sin \phi) \dot{\phi} + \omega r R\sin \phi = ur\cos \phi
$$
After another series of calculations this second equation can be simplified into:
$$
	\dot{\phi} = \frac{r}{R} \omega \cos \phi - \omega
$$
Using the change of variables $\theta=\omega t$ we find that:
$$
	\frac{d}{d\theta} = \frac{d}{d(\omega t)} = \frac{1}{\omega} \frac{d}{dt}
$$
And so,
$$
	\frac{dR}{d\theta} = r\sin \phi - \frac{u}{\omega} \qquad \frac{d\phi}{d\theta} = \frac{r}{R}\cos \phi -1
$$
Define the new variables $u=k\times(\text{Speed of duck})=k\omega r$ and $x=R /r$. Which can be used to simplify this system of equations to the final form:
$$
	\begin{align}
	x' & =\sin \phi-k \\
	\phi' & = \frac{\cos \phi}{x} -1
	\end{align}
$$
Notice that there are fixed points $\sin \phi=k$. Recall that $k$ is the ratio between the speed of the duck and the speed of the dog. These fixed points correspond with the point where the dog is slower than the duck, and both of them wander around in circles forever. Neither of them getting closer to the other.
# Conditions Limit Cycles Exist
There are three conditions telling us no limit cycles exist, and just one telling us limit cycles do exist. We begin with the former.

Potential Function:
If $\dot{\vec{x}}=\vec{v}(\vec{x})$ and $\vec{v}(\vec{x})=\nabla V(\vec{x})$. That is, the vector field has a potential function, then limit cycles cannot exist.

Lyapunov Function
$\dot{\vec{x}}=\vec{v}(\vec{x})$, suppose $\vec{x}_{*}$ is a fixed point such that $\vec{v}(\vec{x}_{*})=0$. A Lyapunov function is a function $V(\vec{x})$ such that $V(\vec{x})>0$, $\forall \vec{x}\neq \vec{x}_{*}$ and $V(\vec{x})$ decreases along the flow. That is, $\frac{d}{dt}V(\vec{x}(t))<0$ for $\vec{x}(t)$ obeying $\dot{\vec{x}}=\vec{v}(\vec{x})$.
- Basically, is there exists a Lyapunov function like this, then there is no limit cycle

Dulac's Criterion
For $\dot{\vec{x}}=\vec{v}(\vec{x})$ in a simply connected region of $\mathbb{R}^{2}$. Suppose there exists a function $g(\vec{x})$ such that $\nabla \cdot(g \dot{\vec{x}})=\nabla(g(\vec{x})\vec{v}(\vec{x}))$ is sign definite in $D$. Then there is no limit cycle in $D^{2}$.
