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
Compute the Jacobian matri`x
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
![[Pasted image 20261123183018.png]]