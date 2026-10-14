We begin with an example, called the system of rabbits vs sheep. The basis of this system is that there are a limited number of resources, and both the rabbits and sheep will eat from them.

The model is:
$$
	\dot{x} = x(3-x) - 2xy = x(3-x-2y)
$$
$$
	\dot{y} = y(2-y)-xy = y(2-y-x)
$$
Where $x$ is the population of the rabbits, and $y$ is the population of the sheep.
- Spoiler, in all cases, one of the populations will always die

Lets start our analysis by located the nullclines.
$$
	x=0 \qquad 3-x-y=0  \implies x=3-2y
$$
$$
	y=0 \qquad 2-y-x=0 \implies y=2-x
$$
The fixed points occur at points where the nullclines intersect.

These are points like (0, 0),
$$
	x=0 \implies y=2-x=y=2
$$
$$
	y=0 \implies x=3-2y=3
$$
(0, 2), (3, 0), and (1, 1) the point where $x=3-2y$ and $y=2-x$ intersect.

To analyze the stability of these nodes, we will approximate the system of equations so they are roughly linear around the fixed points.

For (0, 0) the system of equations becomes:
$$
	\dot{x}=3x \qquad \dot{y}=2y
$$
Which results in the matrix,
$$
	A=\begin{bmatrix}
	3 & 0 \\
	0 & 2
	\end{bmatrix}
$$
Two positive eigenvalues. Therefore $I(A)=1$ and this is an unstable node.

At (3, 0) the system is approximately:
$$
	\dot{x} = -3x-6y \qquad \dot{y}=-y
$$
With matrix
$$
	B=\begin{bmatrix}
	3 & -6 \\
	0 & -1
	\end{bmatrix}
$$
This has two negative eigenvalues, and so it is a stable node with $I(B)=1$

Repeating the same thing at the point (0, 2),
$$
	\dot{x}=-x \qquad \dot{y}=-2y-2x
$$
$$
	C=\begin{bmatrix}
	-1 & 0 \\
	-2 & -2
	\end{bmatrix}
$$
Again, a stable node with $I(C)=1$.

All of these have had positive indices so far. So no saddle-nodes have shown up yet.

At the point (1, 1)
$$
	\dot{x} = -x-2y \qquad \dot{y} = -y-x
$$
$$
	D=\begin{bmatrix}
	-1 & -2 \\
	-1 & -1
	\end{bmatrix}
$$
In this case we have one positive and one negative eigenvalue. This is our saddle-node with $I(D)=-1$.

Now, what about limit cycles. There are none in this system, but lets confirm. We know that the index of a limit cycle must be 1.
- That is, the sum of the fixed points inside a fixed points must be +1

- Now, if you draw a graph of the nullclines, you will notice that in all the places a limit cycle could be, a nullcline trajectory goes through it. Trajectories we have studied and understood. So, there cannot be any limit cycles here
# Limit Cycles
A common, and simple example for a stable limit cycle is:
$$
	\dot{r} = r(1-r) \qquad \dot{\theta}=1
$$
Which, just from observation, you may notice there is a stable fixed point in 1D on $r=1$. In the phase plane, this manifests as a stable limit cycle.

Lets tackle this topic with an example. The Dog vs Duck "pursuit problem".

The duck is confined to a circle. It is moving at some radius $r$ with constant velocity $v$. Its trajectory is $v=\omega r$. The dog, however, may start anywhere, at it is always running towards the duck. What will happen in this situation?
- We tackle this next time