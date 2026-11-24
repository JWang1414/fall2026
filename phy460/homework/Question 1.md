1.
Define $y=\dot{x}$ so the original equation becomes:
$$
	\dot{y} + \alpha \lvert y \rvert y + \sin x = \Gamma
$$
So the system of equations is:
$$
	\begin{align}
	\dot{x} & = y \\
	\dot{y} & = \Gamma- \alpha \lvert y \rvert y - \sin x
	\end{align}
$$
Fixed points appear along $y=0$ and $\alpha \lvert y \rvert y+\sin x=\Gamma$. Fixed points therefore appear under the condition that $\sin x=\Gamma$.

Rough work:
$$
	\begin{bmatrix}
	0 & 1 \\
	-\cos x & -2\alpha \lvert y \rvert 
	\end{bmatrix}
$$
Fixed points appear when $y=0$ so this becomes
$$
	\begin{bmatrix}
	0 & 1 \\
	-\cos x & 0
	\end{bmatrix}
$$
Which is the linear centre we were looking for
- Unsure how to find the Liapunov function
---
2a.
Note that:
$$
	\frac{du}{dt} = \frac{1}{2} \left( \frac{dx}{dt} \right)^{2} = \frac{dx}{dt} \frac{d^{2}x}{dt^{2}}
$$
By chain rule:
$$
	\frac{du}{dx} = \frac{du}{dt} \frac{dt}{dx} = \frac{dx}{dt} \frac{d^{2}x}{dt^{2}} \frac{dt}{dx} = \frac{d^{2}x}{dt^{2}}
$$
As needed.
