We begin with a numerical analysis of the logistic map:
$$
	x_{n+1} = rx_{n}(1-x_{n})
$$
This is essentially the discrete-time analog for the logistic equation of population growth. $x_{n}\geq0$ is a dimensionless measure of the population in the $n$-th generation, and $r\geq 0$ is the intrinsic growth rate.

The graph of the logistic equation can be visualized as a simple parabola with maximum $r /4$ at $x=1 /2$. For the our purposes, we will restrict $0\leq r\leq 4$ and $0\leq x\leq 1$.
- This also happens to be where most interesting behaviour occurs

![[Pasted image 20261126133450.png]]
The logistic map.

Suppose we fix $r$ and begin at some initial population $x_{0}$. For small growth rates $r<1$ there is a stable fixed point at $x=0$. So, physically, in this case the population goes extinct.

However, when $1<r<3$, the population eventually reaches a stable steady state.

At $r=3.3$, the population begins to oscillate between two values. $x_{n}$ is repeating every two iterations, and so we call this a period-2 cycle. At $r=3.5$, we observe a period-4 cycle.

![[Pasted image 20261126133723.png]]
The period-4 cycle. Notice how it oscillates between four different values before returning to the original.

As we increase $r$, more and more period doubling occur. We will denote $r_{n}$ as the value of $r$ where a $2^{n}$-cycle first occurs. Then, we finally reach $r_{\infty}\approx 3.569946\dots$
- The successive bifurcations come faster and faster

The convergence is approximately geometric, and the distance between successive transitions shrinks by the constant factor:
$$
	\delta = \lim_{ n \to \infty } \frac{r_{n}-r_{n-1}}{r_{n+1}-r_{n}} \approx 4.669\dots
$$
- This is the Feigenbaum ratio brought up in class

Beyond $r_{\infty}$, so $r>r_{\infty}$, the long-term behaviour turns out to be aperiodic.

![[Pasted image 20261126134135.png]]![[Pasted image 20261126134141.png]]
A plot of the values of $x_{n}$ as a function of the iteration $n$, and its associated cobweb diagram. See how the behaviour is complex and aperiodic. It never repeats.

To see the long-term behaviour for countless values of $r$ we plot what is called the *orbit diagram*. This is essentially a plot of the system's attractor as a function of $r$.

![[Pasted image 20261126134356.png]]
The orbit diagram for the logistic map. Notice that a copy of the orbit diagram appears in miniature.

For $r>r_{\infty}$, the orbit diagram reveals a mixture of order and chaos, with periodic windows interspersed between chaos.
- At $r\approx 3.83$, for example, there appears to be a stable period-3 cycle.

From this point forth, we move into an analytical analysis of the logistical equation.

Consider the map $x_{n+1}=rx_{n}(1-x_{n})$ for $0\leq x_{n}\leq 1$ and $0\leq r\leq 4$. The fixed points will satisfy
$$
	x^* = f(x^*) = rx^*(1-x^*)
$$
Which, as it turns out, implies $x^*=0,1-r^{-1}$. The origin is a fixed point for all $r$, but $1-r^{-1}$ is allowable only if $r\geq 1$.

Stability depends on the quantity $f'(x^*)=r-2rx^*$. Which tells us that the origin is stable for $r<1$ and unstable for $r>1$. On the other hand, the other fixed point is stable in the region $1<r<3$, but unstable for $r>3$.

Graphical analysis reveals that the origin undergoes a transcritical bifurcation occurs at $r=1$. As $r$ is increased further, it eventually undergoes what is called a *flip bifurcation* where $f'(x^*)=-1$ and swaps from stable to unstable.
- Flip bifurcations are often associated with period doubling. In the case of the logistic map, it indeed spawns a 2-cycle

![[Pasted image 20261126144247.png]]
A diagram of the logistic map as $r$ is varied.

Now, what about the 2-cycle for $r>3$? For a two cycle to exist, two conditions must be met:
1. $f(p)=q$ and $f(q)=p$
2. $f(f(p))=p$
Where $p$ and $q$ are fixed points in the second iterate map $f^{2}(x)\equiv f(f(x))$.

![[Pasted image 20261126144549.png]]
The plot of $f^{2}(x)$. Notice that it is quartic, since $f$ is quadratic.

Including the fixed points $x^*=0,1-r^{-1}$ that we have already found, we also obtain the pair of roots:
$$
	p,q = \frac{r+1\pm \sqrt{ (r-3)(r+1) }}{2r}
$$
Which are real for $r>3$, revealing that a 2-cycle exists for $r>3$.
- When they are complex, the 2-cycle doesn't exist

![[Pasted image 20261126144849.png]]
The cobweb diagram reveals a graphical intuition behind the period doubling.

We may furthermore show that the 2-cycle is stable in the region $3<r<1+\sqrt{ 6 }$. To accomplish this, note that $p$ and $q$ are solutions of $f^{2}(x)=x$, and so $p,q$ are fixed points of the second iterate map $f^{2}(x)$. Therefore, the 2-cycle is stable if $p,q$ are stable fixed points for $f^{2}(x)$.

To determine if $p$ is a stable fixed point, compute the multiplier
$$
	\lambda = \frac{d}{dx}f(f(x))_{x=p} = f'(f(p))f'(p) = f'(q)f'(p)
$$
If $x=q$, we obtain the same result, by symmetry.

Substituting in these values we find:
$$
	\lambda=r(1-2q)r(1-2p) = 4+2r-r^{2}
$$
So this 2-cycle is linearly stable for $\lvert 4+2r-r^{2} \rvert<1$ or $3<r<1+\sqrt{ 6 }$.
- This region can be seen in the diagram below, where the 2-cycle is present before bifurcating into a 4.
- It is not particularly worth it to continue using analytical methods beyond this point

![[Pasted image 20261126145345.png]]
A partial bifurcation diagram of the logistic map.

---
# Class notes
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