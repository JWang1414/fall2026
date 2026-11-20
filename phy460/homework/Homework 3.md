# Question 3
![[Pasted image 20261119170159.png]]
Define $y=\dot{x}$ then $\ddot{x}=\dot{y}$
$$
	\dot{y} + by-kx+x^{3}=0
$$
$$
	\begin{align}
	\dot{x} & =y \\
	\dot{y} & = -by-x^{3}+kx
	\end{align}
$$
Nullclines at $y=0$ and:
$$
	-by-x^{3}+kx=0 \implies by=kx-x^{3}
$$
$$
	y = \frac{x(k-x^{2})}{b}
$$
- There appears to be a pitchfork bifurcation at $k=0$. There is just one fixed point when $k<0$, and three when $k>0$
- $b$ swapping from positive to negative (and vice versa) appears to result in the stability of the fixed points swapping

Jacobian matrix:
$$
	\begin{bmatrix}
	0 & 1 \\
	k-3x^{2} & -b
	\end{bmatrix}
$$
Determinant: $3x^{2}-k$ and trace $-b$.

Note from the nullclines we know that the fixed points will appear at points:
$$
	0=\frac{x(k-x^{2})}{b} \implies x(k-x^{2})=0
$$
Which means there are fixed points at $x=0, \pm \sqrt{ k }$ and $y=0$.

At the fixed point $x=0$ the determinant becomes $-k$ with trace $-b$.

When $\Delta<0\implies-k<0\implies k>0$ we have a saddle point.

When $\Delta>0\implies k<0$ there is a stable/unstable node or centre, depending on the value of $b$. $\tau<0\implies-b<0\implies b>0$ implies there is a stable node.
- The other regimes should be pretty obvious from here

At the fixed point $x=\pm \sqrt{ k }$ the determinant becomes $3k-k=2k$.

The analysis with the trace remains the same. Recall that these fixed points exist only if $k>0$ (due to a pitchfork bifurcation). In this case, $k>0\implies\Delta>0$. Which means these two are stable or unstable fixed points.

Considering the value of $b$, it looks like $b>0$ implies two stable nodes, and $b<0$ implies two unstable nodes.

So what about the case when $b=0$? This breaks down in my analysis
$$
	\begin{align}
	\dot{x} & =y \\
	\dot{y} & = -x^{3}+kx
	\end{align}
$$
Nullclines are at $y=0$ and:
$$
	-x^{3}+kx=0 \implies kx=x^{3} \implies k=x^{2}
$$
So we therefore have $y=0$ and $x=\pm \sqrt{ k }$. Two fixed points.

Jacobian matrix:
$$
	\begin{bmatrix}
	0 & 1 \\
	k-3x^{2} & 0
	\end{bmatrix}
$$
This is the same result as the previous matrix. It tells us that $\tau=0$ and $\Delta=3x^{2}-k$. The fixed points must be at $\pm \sqrt{ k }$ this time so $\Delta=2k$.

The two configurations are most likely:
- Centre at (0, 0) with nothing else
- Two centres at $x=\pm \sqrt{ k }$ and a saddle-node at $x=0$, after the bifurcation

- Not really sure how to draw a diagram of this information. To be honest
# Question 4
![[Pasted image 20261119195352.png]]
- Intuitively, imagining this system, I can tell that it will end up moving around in a circle with radius 1. It will move around in a very jerky motion, going around the circle relatively quickly before getting stuck at $\theta=\pi /2$ for a very long time
- I really do not want to try and figure out what $x(t)$ and $y(t)$ look like. Especially when the image of this system in polar coordinates is so clear
![[Pasted image 20261119213117.png]]
- Do not feel like programming but it would probably look something like this in Python
```
# Define the starting positions for r and theta
r = [0.2]
theta = [0]
dt = 0.01

# Compute the differences from the system of eq (just using the Euler method here)
for i in range(1, 1000):
	r.append(r[-1] + r_function(r[-1]) * dt)
	theta.append(theta[-1] + theta_function(r[-1]) * dt)

# Then I can plot images of these arrays
...

# Convert from Polar to Cartesian
x = r * cos(theta)
y = r * sin(theta)

# Plot images of x(t) and y(t)
...
```
