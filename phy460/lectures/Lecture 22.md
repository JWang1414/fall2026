Last time we re-wrote the logistic map $x_{n+1}=rx_{n}(1-x_{n})$ to the new variables $z$ and $\lambda$ where
$$
	\lambda=\frac{r^{2}}{4}-\frac{r}{2}
$$
- $z$ is also re-scaled, but it's not as important

From this we obtained the new, approximate version of the logistic map
$$
	\begin{align}
	z_{n+1} & = \lambda-z^{2}_{n} \\
	z_{n+2} & = \phi(\lambda) - z^{2}_{n} \\
	z_{n+4} & = \phi(\phi(\lambda)) - z^{2}_{n} \\
	z_{n+8} & = \phi(\phi(\phi(\lambda))) - z^{2}_{n}
	\end{align}
$$
- This is called the "re-normalization group" rescaling
Where we have:
$$
	\phi(\lambda)=-2\lambda(\lambda-\lambda^{2})
$$

The fixed point in $z_{n+1}$ is unstable when $\lambda=3 /4$, or $r=3$, as we know. Now, something very interesting occurs. We know that $z_{n+2}$ represents the second iteration, the 2-cycle. Because it has the same form as $z_{n+1}$, it will be unstable when $\phi(\lambda)=3 /4$. This continued for every iteration. They all become unstable when $\phi ^{k}(\lambda)=3 /4$.

Note that by looking at a graph of $\lambda$ and $\phi(\lambda)$, it is possible to determine the points at which $\phi ^{k}(\lambda)=3 /4$. Simply go to the point $\lambda_{*}$ where $\phi(\lambda_{*})=3 /4$. Then, do a reverse cobweb construction, going over to the diagonal $\lambda$, and back to $\phi(\lambda)$. The point of intersection here is a new value of $\lambda_{*}$ such that $\phi(\phi(\lambda_{*}))=3 /4$.

We can infinitely repeat this reverse cobweb construction method to determine where $\phi ^{\infty}(\lambda)= 3/4$.
- Using this method we can try to approximate the Feigenbaum ratio. I think in class we get a value of $4+\sqrt{ 3 }$. This is a little bit off, but it's close

Period doubling and chaos may also be seen in the Rossler system:
$$
	\begin{align}
	\dot{x} & = -y-z \\
	\dot{y} & = x+ay \\
	\dot{z} & = b+z(z-c)
	\end{align}
$$
If you isolate the long term behaviour in $x$ when $c=5$, you could get some chaotic, aperiodic cycle. Not dissimilar to what we have seen previously. If you construct the Lorenz map of this cycle, you will notice something very similar to have we have seen before. It is qualitatively similar to the logistic map. Furthermore, it exhibits the same $\lvert f'(x) \rvert>1$ we have come to expect to see unstable and chaotic behaviour in for maps
- Remember that a Lorenz map is a map of $x_\text{max}^{n}$ to $x_\text{max}^{n+1}$
# Tent Map
We define the tent map to be:
$$
	f(x) = \begin{cases}
	2rx & x<1 /2 \\
	2r-2rx &  x>1 /2
	\end{cases}
$$
This map is not differentiable, because of the discontinuity at $x=1 /2$. Furthermore, this map has no stable fixed points, the derivative is always greater than 1.
- There are no cycles in the map. No stable fixed points

The same argument used here is the one that is used to show that there are no stable limit cycles or fixed points in the Lorenz attractor.
# Fractals
Loosely speaking fractals are complex geometric shapes, often with self-similarities.

Imagine we have a line $S_{1}$ of length 1. Split it into three, and use the two outer segments for $S_{2}$. The length of $S_{2}$ is $2\times 1 /3$. Repeating this for $S_{3}$, the length will be $2^{2}\times(1 /3)^{2}$.
- We will discuss this in more detail later.
