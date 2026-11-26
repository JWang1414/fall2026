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
Use the change of variables $x=N^{-1}$:
$$
	\dot{N} = -\frac{\dot{x}}{x^{2}} \qquad rN\left( 1-\frac{N}{K(t)} \right) = \frac{r}{x}\left( 1-\frac{1}{xK(t)} \right)
$$
So the original equation becomes:
$$
	\dot{x}+rx = \frac{r}{K(t)}
$$
Solve this ODE with an integrating factor:
$$
	\begin{align}
	\dot{x}+rx & = \frac{r}{K(t)} \\
	e^{ rt }\dot{x} + re^{ rt }x & = \frac{re^{ rt }}{K(t)} \\
	\frac{d}{dt}e^{ rt }x & = \frac{re^{ rt }}{K(t)}
	\end{align}
$$
Integrating both sides and solving for $x(t)$ reveals:
$$
	x(t) = e^{ -rt } \left( \int \frac{re^{ rt }}{K(t)} \, dt +C \right)
$$
Which has a unique solution because $K(t)$ is a positive, smooth function.
- This solution is the limit cycle the system converges to
# Question 1
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
Fixed points appear along $y=0$ and $\alpha \lvert y \rvert y+\sin x=\Gamma$. Fixed points therefore appear under the condition that $\sin x=\Gamma$. Compute the Jacobian matrix to classify these fixed points:
$$
	\begin{bmatrix}
	0 & 1 \\
	-\cos x & -2\alpha \lvert y \rvert 
	\end{bmatrix} =
	\begin{bmatrix}
	0 & 1 \\
	-\cos x & 0
	\end{bmatrix}
$$
Which has eigenvalues $\pm i\sqrt{ \cos x }$. Note that since $x$ is an angle, it is necessarily bounded by $0<x<2\pi$. So the fixed points occur at $\arcsin\Gamma$ and $\pi-\arcsin\Gamma$.

For the fixed point $x=\pi-\arcsin\Gamma$, $\cos x<0$ and the two eigenvalues are real with opposite signs. This is therefore a saddle. In the case where $x=\arcsin\Gamma$, $\cos x>0$ and the fixed point is predicted to be a linear centre. I will use the Lyapunov function $V=y^{2} /2-\Gamma x-\cos x$ to show that this is a stable spiral.
$$
	\begin{align}
	\dot{V} & = y\dot{y} - \Gamma \dot{x} + \dot{x} \sin x \\
	 & = y(\Gamma- \alpha \lvert y \rvert y - \sin x) - \Gamma y + y\sin x \\
	 & = -\alpha \lvert y \rvert y^{2}
	\end{align}
$$
$\dot{V}<0$ for all $y\neq 0$, and $\dot{y}=\Gamma-\sin x\neq 0$ on the line where $y=0$. I conclude that this is a stable spiral.

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

---
2b.
Multiply both sides by $e^{ 2\alpha x }$ after a small re-arrangement:
$$
	\begin{align}
	\frac{du}{dx} + 2\alpha u & =\Gamma-\sin x \\
	e^{ 2\alpha x } \frac{du}{dx} + 2\alpha e^{ 2\alpha x }u & = e^{ 2\alpha x }(\Gamma-\sin x) \\
	\frac{d}{dx}ue^{ 2\alpha x } & = e^{ 2\alpha x }(\Gamma-\sin x)
	\end{align}
$$
Integrate both sides to obtain a general representation for $u(x)$:
$$
	\begin{align}
	\int_{0}^{x} \frac{d}{dx'}ue^{ 2\alpha x' } \, dx'  & = \int_{0}^{x} e^{ 2\alpha x' }(\Gamma-\sin x') \, dx' \\
	u(x)e^{ 2\alpha x } - u(0)  & = \int_{0}^{x} e^{ 2\alpha x' }(\Gamma-\sin x') \, dx'
	\end{align}
$$
Now, $x$ is an angle, and so this system should be periodic over some interval $2\pi$. I will solve for the limit cycle by substituting $x=2\pi$ into the general representation, and requiring $u(0)=u(2\pi)=u_{*}$.
$$
	\begin{align}
	u_{*}(e^{ 4\pi\alpha }-1) & = \int_{0}^{2\pi} e^{ 2\alpha x }(\Gamma-\sin x) \, dx  \\ \\
	 & = \frac{(4\Gamma\alpha^{2}+2\alpha+\Gamma)(e^{ 4\pi\alpha }-1)}{2\alpha(4\alpha^{2}+1)} \\
	u_{*} & = \frac{4\Gamma\alpha^{2}+2\alpha+\Gamma}{2\alpha(4\alpha^{2}+1)}
	\end{align}
$$
Using this fixed point as an initial value $u(0)=u_{*}$ reveals the complete equation for the limit cycle:
$$
	u(x)e^{ 2\alpha x } - \frac{4\Gamma\alpha^{2}+2\alpha+\Gamma}{2\alpha(4\alpha^{2}+1)} = \int_{0}^{x} e^{ 2\alpha x' }(\Gamma-\sin x') \, dx'
$$
The integral on the RHS is:
$$
	= e^{ 2\alpha x } \left[ \frac{\Gamma}{2\alpha} - \frac{2\alpha \sin x-\cos x}{4\alpha^{2}+1} \right] - \frac{4\Gamma\alpha^{2}+2\alpha+\Gamma}{2\alpha(4\alpha^{2}+1)}
$$
So the expression for the limit cycle simplifies into:
$$
	u(x) = \frac{\Gamma}{2\alpha} - \frac{2\alpha \sin x-\cos x}{4\alpha^{2}+1}
$$

---
2c.
Graphically, I note that a homoclinic bifurcation will occur at the point where $u(x)=0$. I am therefore interested in the value of $\Gamma$ such that:
$$
	\frac{\Gamma}{2\alpha} = \frac{2\alpha \sin x-\cos x}{4\alpha^{2}+1} \implies \Gamma = \frac{2\alpha(2\alpha \sin x-\cos x)}{4\alpha^{2}+1}
$$
To determine $\Gamma_{c}(\alpha)$, this expression must be reduced to be in terms of exclusively $\alpha$. Solve for the extrema of $2\alpha \sin x-\cos x$:
$$
	\frac{d}{dx} 2\alpha \sin x-\cos x=0 \implies 2\alpha \cos x+\sin x =0
$$
Which has solutions:
$$
	x=\pi n-\arctan(2\alpha) \qquad n\in \mathbb{Z}
$$
The maximum/minimum values are therefore:
$$
	2\alpha \sin(\pi n-\arctan(2\alpha)) - \cos(\pi n-\arctan(2\alpha)) = \pm\sqrt{ 4\alpha^{2}+1 }
$$
I conclude:
$$
	\Gamma_{c}(\alpha) = \frac{2\alpha \sqrt{ 4\alpha^{2}+1 }}{4\alpha^{2}+1} = \frac{2\alpha}{\sqrt{ 4\alpha^{2}+1 }}
$$
I have dropped the case where $\Gamma_{c}<0$ because $\Gamma>0$ by definition.
# Question 2
![[Pasted image 20261123182922.png]]

Notice that $r=r_{0}$ implies $\ddot{r}=0$. Substituting this into the system of equations:
$$
	0=\frac{h^{2}}{mr_{0}^{3}}-k \qquad \omega_{\theta} = \frac{h}{mr_{0}^{2}}
$$
The first equation reveals the value of $r_{0}$:
$$
	k=\frac{h^{2}}{mr_{0}^{3}} \implies r_{0}^{3} = \frac{h^{2}}{mk} \implies r_{0} = \left( \frac{h^{2}}{mk} \right)^{1/3}
$$
Re-arrange the second equation, and solve for $\omega_{\theta}$ with the help of the first:
$$
	r_{0}^{2} = \frac{h}{m\omega_{\theta}} \implies
	\sqrt{ \frac{h}{m\omega_{\theta}} } = \left( \frac{h^{2}}{mk} \right)^{1/3} \implies
	\omega_{\theta} = \left( \frac{k^{2}}{hm} \right)^{1/3}
$$
So I have:
$$
	r_{0}^{3} = \frac{h^{2}}{mk} \qquad \omega_{\theta}^{3}=\frac{k^{2}}{hm}
$$

![[Pasted image 20261123183000.png]]

Linearize the radial portion of this system into the following representation:
$$
	\begin{align}
	\dot{r} & =v \\
	\dot{v} & = \frac{h^{2}}{m^{2}r^{3}}-\frac{k}{m}
	\end{align}
$$
Compute the Jacobian matrix:
$$
	\begin{bmatrix}
	0 & 1 \\
	-3h^{2} /m^{2}r^{4} & 0
	\end{bmatrix}
$$
Which has the eigenvalues $\pm i \sqrt{ 3 }h /mr^{2}$. The frequency of small radial oscillations is therefore:
$$
	\omega_{r} = \frac{\sqrt{ 3 }h}{mr_{0}^{2}} = \sqrt{ 3 }\omega_{\theta}
$$

![[Pasted image 20261123183006.png]]

$$
	\frac{\omega_{r}}{\omega_{\theta}} = \sqrt{ 3 }
$$
Irrational number. Therefore quasiperiodicity.

![[Pasted image 20261123183011.png]]

According to the previous parts, $\omega_{r}$, $\omega_{\theta}$, and consequently the winding number are all constant. The winding number, which is necessarily a rational or irrational number, corresponds with periodic and quasiperiodic oscillations in $r(t)$ and $\theta(t)$.

Essentially, $r(t)$ and $\theta(t)$ may be plotted on a torus with no chaos, as predicted by the winding number.

![[Pasted image 20261123183018.png]]

Notice that the angular velocity $\dot{\theta}$ is inversely proportional to the radius of rotation such that $\dot{\theta}\propto r^{-2}$. Additionally, the radial acceleration $\ddot{r}$ appears similar to what you might expect from a spring.

I propose this system be modelled by a mass $m$ attached to a spring so the central force is $k$. This entire system is set to rotate, perhaps in some manner of centrifuge. Another possible realization might replace the spring with a magnet, and the mass with a charged object. However it accomplishes the same thing.