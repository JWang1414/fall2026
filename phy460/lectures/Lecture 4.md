Last time, we studied *transcritical bifurcations*. Which use the model:
$$
	\dot{x} = rx-^{2} = x(r-x)
$$
So there is a fixed point at $x=0$ and $x=r$ if $r>0$.

- These bifurcations often show up in phase transitions in magnetism.

Now, we shift our focus to *pitchfork bifurcations*. Initially focused on the supercritical pitchfork bifurcation. Which uses the model equation:
$$
	\dot{x} = rx-x^{3}
$$
Notice that if $x\to -x$, then the equation remains unchanged. This is called $Z_{2}$ symmetry.

This equation can be factored into:
$$
	\dot{x} = x(r-x^{2})
$$
So a fixed point is always at $x=0$. And if $r>0$ there is another pair of fixed points $x=\pm \sqrt{ r }$.
![[Pasted image 20260918122050.png]]
A bifurcation diagram of the fixed points.

Now for the subcritical pitchfork bifurcation.
$$
	\dot{x} = rx+x^{3} - x^{5}
$$
Unlike in the supercritical bifurcation, the $x^{3}$ term is destabilizing, as opposed to stabilizing. The additional $-x^{5}$ term is there to re-stabilize the system, so that it is physically possible.
- We will investigate this system in further detail in the tutorial
# Ising model
Recall that the Ising model takes place in a $d$-dimensional hypercube lattice. Each spot in the grid made up by the lattice is taken up by atoms with spin $\pm 1$.

The Hamiltonian, or energy of this system is:
$$
	H = -J \sum_{\left< ij \right> } s_{i}s_{j} + h \sum_{i} s_{i}
$$
The notation $\left< ij \right>$ is intended to tell us the summation is over only the nearest neighbours. This is 2 in 1D, 4 in 2D and so on. The first term describes the interaction between spins, and the second is the sum of the energy from each of the spins.
- The energy in the interactive term is minimized if all the spins are in the same direction.

See that if $h=0$ the $Z_{2}$ symmetry is intact, but if $h\neq0$ the symmetry is broken.
- Swap $s_{i}\to -s_{i}$ for all $i$ to check the symmetry

For now we will turn off the magnetic field $h$. 

For $J>0$ and $h=0$, the ising model is called ferromagnetic. It is called anti-ferromagnetic when $J<0$
- In the ground state, where all spins are in the same direction, the symmetry is broken (All spin up is different from all spin down). This is called spontaneous symmetry breaking

The magnetization is defined to be the total spin $M=\sum_{i}s_{i}$. That or the average spin. Notice that in the ground state, where temperature is 0, 
$M\neq 0$ because the spins sum to $N$ or $-N$. However, there is some critical temperature such that any temperature hotter has $\left< M \right> =0$.
- Kind of reflected in the fact that, in colder things, the magnetization is stronger
- This is called a magnetic phase transition

Define the order parameter $x$
$$
	M = \left< \frac{\sum_{i}s_{i}}{N} \right>
$$
Neither $M$ or $x$ are symmetric under the $Z_{2}$ transformation $M\to -M$ and $x\to-x$.

Under this parameter the free energy is:
$$
	V(x) = -\frac{1}{2}rx^{2} + \frac{1}{4} x^{4}
$$
The stability is determined by the minima of $V(x)$. Which has extrema at:
$$
	V'(x)=0 =-rx+x^{3}
$$
Which as we can see is identical to the supercritical pitchfork bifurcation.