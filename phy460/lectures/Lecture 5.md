Things to recall from last lecture:
-  Pitchfork bifurcations
- The ising model
# More Ising model
The ising model has:
$$
	H = -\lvert J \rvert \sum_{\left< ij \right> }s_{i}s_{j}
$$
$$
	\left< s \right> = \text{average spin}
$$
Which in our case was:
$$
	\left< S \right> = \tanh\left( \frac{2dJ}{kT} \right)\left< s \right> 
$$
Where $k$ is the Boltzmann constant, $T$ is the temperature, $d$ is the number of dimensions.

What we notice is that a supercritical pitchfork bifurcation occurs at a temperature around 2.264 in 2D space. This corresponds with a phase transition in the magnetization.
- Generally speaking, once the temperature goes below this threshold, the spins will align to be almost all spin up or down

Now we can destabilize this system by adding an external magnetic field to the ising model:
$$
	H = - \lvert J \rvert \sum_{\left< ij \right> } s_{i}s_{j} - h \sum_{i}s_{i}
$$
Which is responsible for breaking the $Z_{2}$ symmetry.

The pitchfork equation with the $Z_{2}$ breaking perturbation is:
$$
	\dot{x} = xr-x^{3} + h
$$
Which has the potential function:
$$
	V(x) = -\frac{r}{2}x^{2} + \frac{x^{4}}{4}-hx
$$
Such that $\dot{x}=-V'(x)$.

If we set $h=0$, the plots of this equation will look something like:
![[Pasted image 20260923123128.png]]

Now what happens if $h\neq 0$? Well the plots begin to look a little lopsided.
- The minimum in the first two will shift over to the right and down a little
- One minimum in the third will move up, but one will go down. So the $h$ field biases one state

There is a special case for the case when $r>0$. When $h$ is large enough, one of the local minima will disappear. So everything that was previously within this state will delay to the other.
- This change is called a "catastrophe"

Now lets go back to $\dot{x}$. To analyze the fixed points, lets set $\dot{x}=0$ and then solve with:
$$
	-rx = -x^{3}+h
$$
This is just a linear line and a cubic function. However, the cubic can move up and down with $h$. So, the number of fixed points will change depending on the values of $r$ and $h$.
- The plot of the fixed points as a function of $x$, $r$, and $h$ looks insane. I'm not even going to try and see if I can include it
- I think it's called the Whitney fold
# Subcritical Pitchfork
$$
	\dot{x} = xr+x^{3}-x^{5} = x(r+x^{2}-x^{4})
$$
Identify the fixed points inside the brackets:
$$
	r+x^{2}-x^{4} =0\implies r=x^{4}-x^{2}
$$
The fixed points of this one look like this:![[Pasted image 20260923125808.png]]
