- Discussion of the orbit maps related to the Logistic and sine maps

Recall that the first iteration map for the Logistic function intersects at just one point. The second iteration map also has just one intersection, but it is not almost tangential to the diagonal. This aspect grows more exaggerated as a include more and more iteration maps. The maps begin to intersect with the diagonal progressively more times.
- This is what is occurring as more cycles are born
- Each intersection is another possible orbit
- Recall that fixed points of the first iteration map always remain fixed points

As more possible orbits appear, there is a "self-similarity" between the orbits. If you plot the iteration maps, you will notice that other fixed points far along the diagonal will appear. The "higher degree" more advanced ones will look the same as the first bifurcation that originally appeared (splitting the orbits from period-1 to period-2).
- You can see the similarity in the birth of the period-3 to period-4
- The fixed points will also appear closer and closer to 1/2
- It is very challenging to get a grasp of this concept without a graphical representation

We will leverage the self similarity in the birth of the $2^{n}$ cycles $\forall n=1, 2,\dots$ and their tendency to appear closer and closer to 1/2.

For our logistic equation we have:
$$
	x_{n+1}=rx_{n}(1-x_{n}) \qquad 0<r<4, x \in[0, 1]
$$
Change to variables $x_{n}=1 /2+z_{n} /r$ so that:
$$
	\frac{1}{2}+\frac{z_{n+1}}{r} = r\left( \frac{1}{2}+\frac{z_{n}}{r} \right) \left( \frac{1}{2}-\frac{z_{n}}{r} \right)
$$
This can eventually be simplified into:
$$
	z_{n+1}=\frac{r(r-2)}{4}-z^{2}_{n} = \frac{r^{2}}{4} - \frac{r}{2} - z^{2}_{n} = \lambda-z^{2}_{n}
$$
We have defined $\lambda=r^{2} /4-r /2$.

Notice that in these variables $x_{n}=1 /2$ is equivalent to $z_{n}=0$. In this space, we pass $r=3$ at $\lambda=3 /4$. This is the regime we are interested in, because it is where the period doubling begins.

Solve for the fixed points:
$$
	z_{*}=\lambda-z^{2}_{*} \implies z_{*} = -\frac{1}{2} + \sqrt{ \frac{1}{4}+\lambda } \implies x_{*}=1-\frac{1}{r}
$$
Additionally $f'(x_{*}) = -2z_{*}$ revealing that fixed points are unstable when $z_{*}=1 /2$ or $\lambda=3 /4$

Now, because $z_{n}=0$ is equivalent to $x_{*}=1 /2$, we have a new map we can study for very small values $z_{n}\to 0$. The first iteration map is $z_{n+1}=\lambda-z^{2}_{n}$ as we already know. The second iteration map is:
$$
	z_{n+2} = \lambda-z^{2}_{n+1} = \lambda - (\lambda-z^{2}_{n})^{2} = \lambda-\lambda^{2} + 2\lambda z^{2}_{n} - z^{4}_{n}
$$
Since we are studying small values, we can ignore $z^{4}_{n}$.

We will now define an adjusted set of variables:
$$
	z_{n}\to -\frac{z_{n}}{2\lambda} \qquad z_{n+2} \to -\frac{z_{n+2}}{2\lambda} \qquad \lambda\to-2\lambda(\lambda-\lambda^{2})
$$
The second iteration map (including our approximation) now looks like:
$$
	z_{n+2}=-2\lambda(\lambda-\lambda^{2})-z^{2}_{n}
$$
Which now looks almost identical to the first iteration map.

We may simplify the representation of $z_{n+2}$ by representing the collection of $\lambda$s as $\phi(\lambda)$.
- I am not entirely sure about the logistics of $\phi$

The iteration maps may now be written out like:
$$
	\begin{align}
	z_{n+1} & = \lambda-z^{2}_{n} \\
	z_{n+2} & = \phi(\lambda) - z^{2}_{n} \\
	z_{n+4} & = \phi(\phi(\lambda)) - z^{2}_{n} \\
	z_{n+8} & = \phi(\phi(\phi(\lambda))) - z^{2}_{n}
	\end{align}
$$
And you can see that this recursive pattern continues on forever.
- Note that I have dropped any notation indicating the re-scaling between each equation. These re-scalings still exist, it's just very clunky to say every single equation is being written in a new scale
- We are also ignoring higher order terms here
- We are effectively noting that in higher and higher order terms the physics and general ideas of what's going on are the same (up to some re-scaling)
