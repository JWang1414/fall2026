![[Pasted image 20261123182922.png]]

Notice that $r=r_{0}$ implies $\ddot{r}=0$. Substituting this into the system of equations:
$$
	0=\frac{h^{2}}{mr_{0}^{3}}-k \qquad \omega_{\theta} = \frac{h}{mr_{0}^{2}}
$$
The first equation reveals the value of $r_{0}$:
$$
	k=\frac{h^{2}}{mr_{0}^{3}} \implies r_{0}^{3} = \frac{h^{2}}{mk} \implies r_{0} = \left( \frac{h^{2}}{mk} \right)^{1/3}
$$
Re-arrange the second equation, and solve for $\omega_{\theta}$ with the help of the first:
$$
	r_{0}^{2} = \frac{h}{m\omega_{\theta}} \implies
	\sqrt{ \frac{h}{m\omega_{\theta}} } = \left( \frac{h^{2}}{mk} \right)^{1/3} \implies
	\omega_{\theta} = \left( \frac{k^{2}}{hm} \right)^{1/3}
$$
So I have:
$$
	r_{0}^{3} = \frac{h^{2}}{mk} \qquad \omega_{\theta}^{3}=\frac{k^{2}}{hm}
$$

![[Pasted image 20261123183000.png]]

Linearize the radial portion of this system into the following representation:
$$
	\begin{align}
	\dot{r} & =v \\
	\dot{v} & = \frac{h^{2}}{m^{2}r^{3}}-\frac{k}{m}
	\end{align}
$$
Compute the Jacobian matrix
$$
	\begin{bmatrix}
	0 & 1 \\
	-3h^{2} /m^{2}r^{4} & 0
	\end{bmatrix}
$$
Which has the eigenvalues $\pm i \sqrt{ 3 }h /mr^{2}$. The frequency of small radial oscillations is therefore:
$$
	\omega_{r} = \frac{\sqrt{ 3 }h}{mr_{0}^{2}} = \sqrt{ 3 }\omega_{\theta}
$$

![[Pasted image 20261123183006.png]]

$$
	\frac{\omega_{r}}{\omega_{\theta}} = \sqrt{ 3 }
$$
Irrational number. Therefore quasiperiodicity.

![[Pasted image 20261123183011.png]]

According to the previous parts, $\omega_{r}$, $\omega_{\theta}$, and consequently the winding number are all constant. The winding number, which is necessarily a rational or irrational number, corresponds with periodic and quasiperiodic oscillations in $r(t)$ and $\theta(t)$.

Essentially, $r(t)$ and $\theta(t)$ may be plotted on a torus with no chaos, as predicted by the winding number.

![[Pasted image 20261123183018.png]]

Notice that the angular velocity $\dot{\theta}$ is inversely proportional to the radius of rotation such that $\dot{\theta}\propto r^{-2}$. Additionally, the radial acceleration $\ddot{r}$ appears similar to what you might expect from a spring.

I propose this system be modelled by a mass $m$ attached to a spring so the central force is $k$. This entire system is set to rotate, perhaps in some manner of centrifuge. Another possible realization might replace the spring with a magnet, and the mass with a charged object. However it accomplishes the same thing.
