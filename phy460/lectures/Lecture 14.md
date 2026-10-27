Recall the van der Pol oscillator:
$$
	\ddot{x} + \mu \dot{x}(x^{2}-1)+x=0
$$
Last time, we simplified this into a system of equations using the substitutions:
$$
	y= \frac{1}{\mu}(\dot{x} + \mu F(x)) \qquad F(x) = \frac{x^{3}}{3}-x
$$
Resulting in:
$$
	\begin{align}
	\dot{y} & = -\frac{1}{\mu}x \\
	\dot{x} & = \mu(y-F(x))
	\end{align}
$$
This has nullclines at $x=0$ and $y=F(x)$.
- Visualizing this system, we essentially have a limit cycle where we are going in a loop defined by $y=F(x)$
- This limit cycle has a bifurcation, which occurs when $\mu=0$, and then system become a harmonic oscillator

Now, we look at another oscillator, one which models a circuit:
$$
	V+L\dot{I} + V_\text{diode}(I) =0 \qquad \dot{V}= \frac{I}{C}
$$
Where the diode here is pretty complex. It's a tunneling diode. With reference to our van der Pol oscillator, we can see that it is similar with $w=-V$, $x=I$, and $\mu F=V_\text{diode}(I)$.
# Bifurcations in 2D
It is pretty challenging to draw intuitive diagrams of the bifurcations, because we need 3 dimensions to accomplish this. Instead, we will try to visualize them with the nullclines.

Recall that fixed points appear when the nullclines intersect. So we can see where bifurcations might appear by seeing how the nullclines change as we alter some parameter.

![[Pasted image 20261027181429.png]]
An example of a saddle-node bifurcation in 2D.

![[Pasted image 20261027181647.png]]
An example of a supercritical pitchfork in 2D.

The same transcritical and pitchfork bifurcations from 1D translate pretty 1-to-1 in 2D. However, the most interesting case occurs for *Hopfield bifurcations*, which include limit cycles.
# Hopfield Bifurcations
As an example, we will study a supercritical Hopfield bifurcation:
$$
	\begin{align}
	\dot{r} & = r(\mu-r^{2}) \\
	\dot{\theta} & = \omega+br^{2}
	\end{align}
$$

![[Pasted image 20261027182212.png]]
As $\mu$ is adjusted, the spiral swaps from stable to unstable.

Now, convert to Cartesian coordinates:
$$
	\begin{bmatrix}
	\dot{x} \\
	\dot{y}
	\end{bmatrix} = \begin{bmatrix}
	\mu & -\omega \\
	\omega & \mu
	\end{bmatrix} \begin{bmatrix}
	x \\
	y
	\end{bmatrix}
$$
When $\mu<0$ there is no limit cycle and the eigenvalues are:
$$
	\lambda_{\pm} = -\lvert \mu \rvert \pm i\omega
$$
Otherwise the eigenvalues are:
$$
	\lambda_{\pm} = \mu\pm i\omega
$$
In this second case we have a stable and unstable spiral. But both fixed points are covered by a limit cycle.

To imagine how this changes as $\mu$ changes from positive to negative, imagine the limit cycles centred at some fixed point. As $\mu\to 0$, the limit cycles shrink before eventually annihilating themselves.

Lets try another example, this time with:
$$
	\begin{align}
	\dot{r} & = r(\mu-r^{2}) \\
	\dot{\theta} & = \omega+br^{2}
	\end{align}
$$
See that when $\mu>0$ there are no fixed points in $r$, but there is a fixed point at $\sqrt{ \lvert \mu \rvert }$ when $\mu<0$.

Generally speaking, for supercritical Hopfield bifurcations:
1. The size of the limit cycle grows continuously from zero, and increases proportional to $\sqrt{ \mu-\mu_{c} }$ for $\mu$ close to $\mu_{c}$
2. The frequency of the limit cycle is given approximately by $\omega=\mathrm{Im}\lambda$, evaluated at $\mu=\mu_{c}$. The formula is exact at the birth of the limit cycle, and correct within $O(\mu-\mu_{c})$ for $\mu$ close to $\mu_{c}$. The period is therefore $T=(2\pi /\mathrm{Im}\lambda)  + O(\mu-\mu_{c})$

Lets look at another equation. This time, we will introduce a new way of determining if a system possess a limit cycle.
$$
	\ddot{x} + \alpha \dot{x} + \sin x = \Gamma
$$
Where $\Gamma$ is some constant torque. Now, linearize this into the system:
$$
	\dot{x}=y \qquad \dot{y} = \Gamma-\sin x - \alpha y
$$
We would like to show that there exists some unique limit cycle when $\Gamma>1$.

Fix $x \in(-\pi, \pi)$. Then there are nullclines at $y=0$ and $y=(\Gamma-\sin x) /\alpha$.
- Adjusting $\Gamma$ will shift the sine function up or down

We will conclude the study of this system after the reading week.