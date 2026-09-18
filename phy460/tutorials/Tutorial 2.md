Ising model again.

$$
	H = - J \sum_{\left< ij \right> } s_{i}s_{j} \qquad \left< M \right>  = \left< \frac{\sum_{i}s_{i}}{N} \right>
$$
The Hamiltonian and the order parameter.

Generally speaking, $\left< M \right> =0$ to $\left< M \right> \neq =0$ corresponds with a phase transition.
- This has some association with the $Z_{2}$ symmetries

Recall our discussion of the free energy:
$$
	V(x) = -\frac{r}{2}x^{2} + \frac{1}{4}x^{4} \implies -V'(x) = rx-x^{3}
$$
This is a supercritical pitchfork bifurcation such that there is just one fixed point when $r<0$ and 3 when $r>0$.

For $r\propto T_{c}-T$ the single fixed point corresponds to the magnet being above critical temperature. As the magnet is cooled, the bifurcation occurs.
- Specifically $\left< M \right>$ is what is bifurcating here

Now, recall that all functions in 1D have a potential function:
$$
	\dot{x} = f(x) =-\frac{d}{dx}V(x)
$$
And the extrema of $V$ correspond with the zeros of $f$. The minima of $V$ are stable fixed points, maxima are unstable, and saddles are semi-stable.

While the partition function and the surprise can be found in several ways in 1D, in 2D the solution is quite complex. It is unsolved in 3D.

In 2D the critical temperature is $k_{B}T_{c}=2.269$ joules. In 3D it is approximately $k_{B}T_{c}\approx 4.5$ joules.
# Mean Field Solution
A common simplification of the ising model is to solve it with the mean field approximation.

The mean field is essentially:
$$
	s_{i} = \left< s \right> + \delta s_{i}
$$
Now, note that each atom interacts with $2d$ neighbours. Under this approximation we have:
$$
	H(s_{0})=-J \sum_{\left< ij \right> } s_{0}s_{i} \to -J 2d\left< s \right> s_{0}
$$
Where $s_{0}$ is represents some random particle with spin $s_{0}$.

Compute the partition function:
$$
	\mathcal{Z}(\left< s \right> ) = \sum_{s_{0}=\pm 1} e^{ \beta J_{2}d\left< s \right> s_{0} }
$$
For a single spin. And,
$$
	\left< s \right> = \frac{\sum_{s_{0}\pm 1}s_{0}e^{ \beta J_{2}d\left< s \right> s_{0} }}{\sum_{s_{0}'=\pm 1} e^{ \beta J_{2}d\left< s \right> s_{0}' }}
$$
Notice that this function simplifies:
$$
	\left< s \right> = \tanh(2\beta Jd\left< s \right> )
$$
To see how this works we plot:
$$
	s=\tanh(2\beta Jds)
$$
And, just as we would expect, there are three intersections between $\tanh$ and $s$.

We find the critical temperature from the condition:
$$
	\frac{2Jd}{kT_{c}}=1
$$
- I believe this has something to do with the slope or intersections, but I'm not sure