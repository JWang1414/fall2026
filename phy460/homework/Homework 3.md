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
# Question 5
![[Pasted image 20261121165850.png]]
- Independent of $\theta$. I will therefore focus exclusively on $r$

Find fixed points:
$$
	r(\mu-\sin r)=0 \implies r=0, \mu-\sin r=0
$$
$$
	\sin r=\mu
$$
- Clearly, there is a permanent fixed point at $r=0$
- When $-1<\mu<1$, there is an infinite number of fixed points. The bifurcations occur at $\mu=1$ and $\mu=-1$.
- When $\mu\to-1$ from below, or $\mu\to 1$ from above, the movement along the $r$-axis grows increasingly jerky around where the fixed points will appear
- Since $\dot{\theta}=1$, solutions will go around and around in cycles

In the regime where $\mu<-1$, there is just one fixed point at the origin. It is globally attracting.

When $\mu=-1$, the bifurcation occurs. All at once, semi-stable fixed points occur at points where $\sin r=-1$. That is, starting at $3\pi /2$, and repeating every interval of $2\pi$. Between these fixed points, solutions are attracted to the centre, but they stop at the semi-stable fixed points.

When $-1<\mu<1$ the semi-stable fixed points split into stable/unstable pairs, in an infinite series of saddle-node bifurcations As $\mu$ grows closer and closer to either $-1$ or $1$, the fixed points get closer to each other, preparing to annihilate each other.

When $\mu=1$ the fixed points collide, becoming a series of semi-stable fixed points at points where $\sin r=1$, which begin at $\pi /2$, and repeat at intervals of $2\pi$. The behaviour now has reversed however. The system is repelling, pushing solutions away into further semi-stable fixed points, as opposed to pulling them to the centre.

When $\mu>1$, there is once again just one fixed point at the origin. It is globally repelling.
# Question 1 (Not done)
---
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

# Question 6
![[Pasted image 20261121230809.png]]
![[Pasted image 20261121230816.png]]
I define $0<K_\text{min}<\min\{ K(t) \}$ and $K_\text{max}>\max\{ K(t) \}$. This is possible because $K(t)$ is a positive, smooth function.

Note that in this region, $N>0$ because $K_\text{min}>0$. Therefore the flow $\dot{N}$ is positive along $K_\text{min}$:
$$
	\dot{N} = rN\left( 1-\frac{N}{K(t)} \right) = rN\left( 1-\frac{K_\text{min}}{K(t)} \right)>0
$$
Using the same argument the flow is negative along $K_\text{max}$.

Since this equation is $T$-periodic in $t$. I bound this problem within $K_\text{min}$, $K_\text{max}$, 0, and $T$. Furthermore, I define the Poincare map which maps some initial point $n$ to $P(n)$. I want to show that there is some fixed point $n^*=P(n^*)$.

Consider a trajectory at begins at $n=K_\text{min}$. Then, because the flow is upwards along the entirety of $K_\text{min}$, $P(K_\text{min})>K_\text{min}$. Using the same argument, we also have $P(K_\text{max})<K_\text{max}$.

$P(n)$ must be a continuous, monotonic function. This arises because $\dot{N}$ is smooth, and if $P(n)$ were not monotonic, two trajectories would cross, or overlap.

Then, by the intermediate value theorem, $P(n)$ must cross the 45 degree diagonal at some point $n^*$ such that $n^*=P(n^*)$.
![[Pasted image 20261121235340.png]]
