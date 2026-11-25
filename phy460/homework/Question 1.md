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

---
2b.

Rough work:

The solution to the linear ODE is:
$$
	u(x) = \frac{\Gamma+4\alpha^{2}\Gamma + 2\alpha \cos x-4\alpha^{2}\sin x}{8\alpha^{3}+2a} + c_{1} e^{ -2ax }
$$
The exponential will decay to zero as $x\to \infty$, so I assume that the limit cycle is this first segment:
$$
	u(x) = \frac{\Gamma+4\alpha^{2}\Gamma + 2\alpha \cos x-4\alpha^{2}\sin x}{8\alpha^{3}+2a}
$$
Which is indeed periodic, since the only non-constant section is:
$$
	2\alpha(\cos x-2\alpha \sin x)
$$
- I suppose in the last section I am trying to find the point where this limit cycle comes into contact with the $x$-axis at $u(x)=0$?
