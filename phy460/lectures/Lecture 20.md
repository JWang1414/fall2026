Recall that we were discussing the idea of uni-modular maps with a single maximum $f''(x)<0$.

Maps are defined as: $x_{n}\to x_{n+1}=f(x_{n})$. Which essentially tells us what the next value is from the current value. We will be studying maps on $x_{n}\in[0, 1]$.

Today we would like to show that $\lvert f'(x_{*}) \rvert<1$ implies stability, and $\lvert f'(x_{*}) \rvert>1$ implies instability.

Our study will focus on the logistic map $x_{n+1}=rx_{n}(1-x_{n})$.

- Last time we showed that this is stable for $1<r<3$ with a fixed point at $1-r^{-1}$.
- When $r<1$ there is a fixed point at 0

However, in the case where $r>3$, 1 cycle becomes unstable, and 2 stable cycles in the map appear.
- Says this is a fixed point of 2nd iteration of $f(x)$. Not sure what this means

In our notation, we will say that $f_{n}(x)$ is the $n$-th iteration of the map. Note that a fixed point of $f(x)$ is also a fixed point of $f_{2}(x)$.

Notice that the 2nd iteration is also equivalent to $f(f(x))$. Therefore,
$$
	f'_{2}(x) = \frac{d}{dx}f(f(x)) = f'(f(x))f'(x)
$$
- Since our map is uni-modular, $x_{0}$ is its max such that $f'(x_{0})=0$

Because $x_{0}$ is an extremum for $f(x)$, it is also an extremum for $f_{2}$:
$$
	f_{2}'(x_{0}) = f(f(x_{0}))f'(x_{0}) =0
$$

Let $x_{1}$ be the pre-image of $x_{0}$ such that $f(x_{1})=x_{0}$. Now, $x_{1}$ must also be an extremum of $f_{2}$:
$$
	f_{2}'(x_{1}) = f'(f(x_{0}))f'(x_{1}) = f'(x_{0})f'(x_{1}) =0
$$
What happens if we take the second derivative of $f_{2}$?
$$
	f_{2}''(x) = f''(f(x))(f'(x))^{2} + f'(f(x))f''(x)
$$
If you plug in $x_{0}$, you will see that $f_{2}''(x_{0})>0$, and so $x_{0}$ is actually a minimum for $f_{2}$. But what about at $x_{1}$? Well, you will find that $f_{2}''(x_{1})<0$. So the pre-images at $x_{1}$ are maxima.

- Most interestingly, we find that as we increase $r$, the fixed point $x_{*}$ of $f$ and $f_{2}$ undergoes another bifurcation. Splitting into 1 unstable fixed point and 2 stable points.
- The fixed points will continue to bifurcate until there are an infinite number of fixed points

If we define $r_{n}$ as the value of $r$ where the $2^{n}$-th cycle is born, we find the Feigenbaum ratio:
$$
	\lim_{ n \to \infty } \frac{r_{n}-r_{n-1}}{r_{n+1}-r_{n}} \approx 4.669\dots
$$
Which is true for all uni-modular maps