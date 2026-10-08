# Question 1
---
Gompertz' law
$$
	\ln(bN) =0 \implies bN=1 \implies N = \frac{1}{b}
$$
Unstable fixed point at $N=0$ and stable fixed point at $N=b^{-1}$.

Solve for $f'(x^*)$ to find the characteristic time scale, which is defined to be $\lvert f'(x^*) \rvert^{-1}$.

For some vector field $f(x)$ and fixed point $x^*$, recall that the characteristic time scale is defined to be: $\lvert f'(x^*) \rvert^{-1}$. First compute the derivative:
$$
	\frac{d}{dN} \left[ -aN \ln(bN) \right]  = -a \frac{d}{dN} N\ln(bN) = -a(\ln(bN)+1)
$$

When $N\to 0$, $\ln(bN)\to-\infty$ and therefore $-a[\ln(bN)+1]\to \infty$. Implying that the fixed point at $N=0$ is highly unstable with characteristic time scale 0. At the other fixed point $N=b^{-1}$,
$$
	-a(\ln(bN)+1) = -a\left[ \ln\left( \frac{b}{b} \right)+1 \right] = -a(0+1)=-a
$$
So the fixed point at $N=b^{-1}$ is stable with characteristic time scale $a^{-1}$.

---
$$
	x-x^{3} = x(1-x^{2}) = x(1-x)(1+x)
$$
Unstable fixed point at $x=0$ and stable fixed points at $x=\pm 1$.

Compute derivative:
$$
	\frac{d}{dx}\left[ x-x^{3} \right] = 1-3x^{2}
$$
When $x=0$, $1-3x^{2}=1-0=1$. Positive. Confirms unstable fixed point with characteristic time scale 1.

When $x=\pm 1$, $1-3x^{2}=1-3=-2$. Stable fixed points with characteristic time scale 1/2.

$x-x^{3}$ can be factored into $x(1-x)(1+x)$, revealing that is has three fixed points at $x=0, \pm 1$. The fixed point $x=0$ is unstable with characteristic time scale 1. The fixed points $x=\pm 1$ are stable with characteristic time scale 1/2.

---
$$
	1+\frac{1}{2}\cos x
$$
Always positive. Has no fixed points.

$1+\frac{1}{2}\cos x$ is always positive, and so has no fixed points. Qualitatively, because the function is shaped like a "wave" $x(t)$ should periodically speed up and slow down as it is increasing.

---
$$
	e^{ x } - \cos x
$$
Infinite number of fixed points when $e^{ x }=\cos x$.

Beginning with an unstable fixed point at $x=0$, stable fixed point at $x\approx-1.29$, and alternating between unstable and stable from there.

Approximate with $-\cos x$.
$$
	\frac{d}{dx}\left[ -\cos x \right] = \sin x
$$
$\sin x$ is negative for $-\left( 2n+\frac{1}{2} \right)\pi$ and positive for $-\left( 2n+\frac{3}{2} \right)\pi$. Where $n\in \mathbb{N}$. This roughly means that the fixed points with "even" $\pi$ are stable and the ones corresponding with "odd" $\pi$ are unstable.

$e^{ x }-\cos x$ has an infinite number of fixed points when $e^{ x }=\cos x$. Moving from right to left, an unstable fixed point is found at $x=0$, and a stable fixed point at $x\approx-1.29$. The fixed points alternative between stable and unstable as you progress to the left (to $-\infty$). Roughly speaking, the fixed points can be approximated with $-\cos x$. Performing linear stability analysis reveals that the fixed points near $-\left( 2n+\frac{1}{2} \right)\pi$ are stable and unstable for $-\left( 2n+\frac{3}{2} \right)\pi$, where $n\in \mathbb{N}$. Roughly speaking, these correspond with "even" ($2n$) and "odd" ($2n+1$) fixed points.
# Question 2
Beginning with the logistic equation,
$$
	\dot{N} = aN(1-cN)
$$
Use the substitution $N=x /c$,
$$
	aN(1-cN) = a\left( \frac{x}{c} \right) \left( 1-c\left( \frac{x}{c} \right) \right) = \frac{a}{c}x(1-x)
$$
Which reduces to the standard form $\dot{x}=x(1-x)$ after a scaling of $c /a$. To solve this equation, first re-arrange:
$$
	\frac{dx}{dt} = x(1-x) \implies \frac{1}{x(1-x)} \, dx = dt
$$
Then integrate:
$$
	\int_{x_{0}}^{x} \frac{1}{x(1-x)} \, dx = \int_{x_{0}}^{x} \frac{1}{x}- \frac{1}{1-x} \, dx = \ln\left( \frac{1-x_{0}}{x_{0}} \frac{x}{1-x} \right)
$$
Therefore:
$$
	\ln\left( \frac{1-x_{0}}{x_{0}} \frac{x}{1-x} \right) =t \implies x = \frac{e^{ t }}{k+e^{ t }}
$$
Where I have defined $k=(1-x_{0}) /x_{0}$. Multiply the top and bottom by $e^{ -t }$ to obtain the most characteristic form:
$$
	x(t) = \frac{1}{1+ke^{ -t }}
$$
# Question 4
The vector fields and bifurcation diagrams for $\dot{x}=1+rx+x^{2}$. There are two saddle-node bifurcations which occur at $r=\pm 2$. The dotted lines indicate unstable fixed points, and the solid lines stable ones.

The vector fields and bifurcation diagrams for $\dot{x}=r-\cosh(x)$. There is one saddle-node bifurcation at $r=1$.

The vector fields and bifurcation diagrams for $\dot{x}=r^{2}-x^{2}=(r+x)(r-x)$. There is a transcritical bifurcation at $r=0$.

The vector fields and bifurcation diagrams for $\dot{x}=x(r-e^{ x })$. Note that there is a permanent fixed point at $x=0$, I have notated the stability of this fixed point along the axis with small arrows. There is a transcritical bifurcation at $r=1$.

The vector fields and bifurcation diagrams for $\dot{x}=rx-\ln(1+x)$. Once again, there is a permanent fixed point at $x=0$. There is a transcritical bifurcation at $r=1$.

The vector fields and bifurcation diagrams for $\dot{x}=x+\tanh(rx)$. There is a subcritical pitchfork bifurcation at $r=-1$.

The vector fields and bifurcation diagrams for $\dot{x}=rx+x^{3}/(1+x^{2})$. There is a subcritical pitchfork bifurcation at $r=0$. Unlike the previous bifurcation, the outer two prongs of the pitchfork diverge to infinity at $r=-1$.
# Question 5
Phase portait on the circle for $\dot{\theta}=\sin ^{3}\theta$. This vector field has period $2\pi$. There is an unstable fixed point at $\theta=0$ and stable fixed point at $\theta=\pi$.

Phase portait on the circle for $\dot{\theta}=\sin\theta + \cos\theta$. Vector field has period $2\pi$. Stable fixed point at $3\pi /4$ and unstable fixed point at $7\pi /4$.

Phase portait on the circle for $\dot{\theta}=\sin(k\theta)$. Vector field now has period $2\pi /k$. Unstable fixed point at $\theta=0$ and unstable fixed point at $\theta=\pi /k$.

# Question 6
$$
	\dot{\theta} = \frac{\sin \theta}{\mu+\cos \theta}
$$
Since $\sin\theta$ is in the numerator, there are permanent fixed points at $\sin\theta=0$. That is, periodically with period $\pi$. These fixed points will oscillate in stability. The denominator incurs more complex behaviour within $-1<\mu<1$. For simplicity, I will model the asymptotes the vector field as fixed points.

Case: $\mu<-1$
- Stable fixed point at $\theta=0$
- Unstable fixed point at $\theta=\pi$

Case: $-1<\mu<1$
- Four fixed points in total
- Unstable fixed point at $\theta=0$
- Stable fixed point at $\theta=\pi$
- Two stable fixed points moving from $\theta=0$ to $\theta=\pi$
- This case can be imagined as two supercritical pitchfork bifurcations. The bifurcations occur at $\mu=-1$ and $\mu=1$. The two pitchforks "merge together"

Case: $\mu>1$
- Unstable fixed point at $\theta=0$
- Stable fixed point at $\theta=\pi$

$$
	\dot{\theta} = \mu+\sin\theta + \cos(2\theta)
$$
This vector field has a series of saddle-node bifurcations as $\mu$ is varied. Specifically, bifurcations occur at $\mu=-1.125, 0, 2$.

At $\mu=-1.125$ there are two saddle node bifurcations with two semi-stable fixed points in total. When $-1.125<\mu<0$, there are four fixed points. Two stable and two unstable fixed points.

At $\mu=0$, two of the fixed points merge into one semi-stable fixed point. The two annihilate each other, in another saddle-node bifurcation. As a result, when $0<\mu<2$, there is one stable fixed point, and one unstable fixed point.

At $\mu=2$, the final two remaining fixed points merge together in another saddle-node bifurcation. There is now just one semi-stable fixed point. In all other cases, $\mu<-1.125$ and $\mu>2$, there are no fixed points.
# Question 3
---
a.
$N$ is constant means that $\dot{N}=0$. Want to show that:
$$
	\dot{S}+\dot{I} + \dot{R}=0
$$
By direct substitution:
$$
	-\beta SI + \left[ \beta SI - \alpha I \right]  + \alpha I = -\beta SI + \beta SI - \alpha I  + \alpha I =0
$$
---
b.
Re-arrange the expression for $\dot{R}$ in terms of $I$:
$$
	\dot{R} = \alpha I \implies I = \frac{\dot{R}}{\alpha}
$$
Substitute into $\dot{S}$:
$$
	\dot{S} = -\beta S\left( \frac{\dot{R}}{\alpha} \right) = -\frac{\beta}{\alpha} S\dot{R}
$$
Swap notation to prepare for an integral:
$$
	\frac{dS}{dt}=-\frac{\beta}{\alpha} S \frac{dR}{dt} \implies \frac{dS}{S}=-\frac{\beta}{\alpha} \frac{dR}{dt} dt = -\frac{\beta}{\alpha} \, dR
$$
Integrate both sides
$$
	\int_{S_{0}}^{S} \frac{1}{S} \, dS = \ln S - \ln S_{0} \qquad \int_{0}^{R} -\frac{\beta}{\alpha} \, dR = -\frac{\beta}{\alpha}R
$$
Where I have assumed that $R_{0}=0$. Equate the two and re-arrange,
$$
	\ln S = -\frac{\beta}{\alpha}R + \ln S_{0} \implies S = e^{ -\beta R/\alpha + \ln S_{0} } = e^{ \ln S_{0} } e^{ -\beta R/\alpha }
$$
Yielding the final expression:
$$
	S(t) = S_{0}\exp\left( -\frac{\beta}{\alpha}R(t) \right)
$$
---
c.
Going back to the expression for $N$:
$$
	S+I+R=N \implies I = N-S-R
$$
Substituting in what was found in part b:
$$
	I = N-R-S_{0}\exp\left( -\frac{\beta}{\alpha} R(t) \right)
$$
According to the definition of $\dot{R}$:
$$
	\dot{R}=\alpha I = \alpha \left[ N-R-S_{0}\exp\left( -\frac{\beta}{\alpha} R(t) \right) \right]
$$
---
d.
Define the following variables:
$$
	u=\frac{\beta}{\alpha}R(t) \qquad \tau= \beta S_{0}t \qquad a=\frac{N}{S_{0}} \qquad b=\frac{\alpha}{\beta S_{0}}
$$
Substituting in these variables, $\dot{R}$ becomes:
$$
	\begin{align}
		\frac{dR}{dt} & = \alpha \left( N - \frac{\alpha}{\beta}u - S_{0}e^{ -u } \right) \\
		 & = \alpha S_{0} \left( \frac{N}{S_{0}} - \frac{\alpha}{\beta S_{0}}u - e^{ -u } \right) \\
		 \frac{1}{\alpha S_{0}} \frac{dR}{dt} & = a-bu-e^{ -u }
	\end{align}
$$
Note that:
$$
\frac{du}{d\tau} = \frac{1}{\beta S_{0}} \frac{\beta}{\alpha} \frac{dR}{dt} = \frac{1}{\alpha S_{0}} \frac{dR}{dt}
$$
Therefore:
$$
	\frac{du}{d\tau} = a-bu-e^{ u }
$$
---
e.
Recall that $a$ and $b$ are defined to be:
$$
	a=\frac{N}{S_{0}} \qquad b=\frac{\alpha}{\beta S_{0}}
$$
$S$, $I$, $R$, $S_{0}$ are necessarily positive. Otherwise they would have no physical meaning. Additionally, $\alpha$ and $\beta$ are both defined to be positive constants. $b$ must therefore also be a positive constant $b>0$.

For $a$, notice that at $t=0$,
$$
	a=\frac{N}{S_{0}} = \frac{S_{0}+I_{0}+R_{0}}{S_{0}} \geq 1
$$
---
f.
Re-arrange so it's easier to analyze:
$$
	a-bu-e^{ -u } =0 \implies a-bu = e^{ -u }
$$
Since $a\geq 1$ and $b> 0$, this function will have 1-2 fixed points.

When $a=1$ and $b=1$, there is a single semi-stable fixed point at $u=0$. Otherwise, there are two fixed points. An unstable fixed point at $u<0$, and a stable fixed point at $u>0$.

---
g.
Recall from the definition of $u$ we have:
$$
	u(t) = \frac{\beta}{\alpha}R(t)
$$
Compute the first derivative:
$$
	\dot{u} = \frac{\beta}{\alpha}\dot{R} = \beta I
$$
Note that $\dot{u}$ is proportional to $\dot{R}$ and $I$. So their extrema will occur at the same time.

---
h.
I will use $du /d\tau$ to determine the behaviour of $\dot{u}$ at $t=0$. The critical points of $du /d\tau$ will occur when:
$$
	\frac{d^{2}u}{d\tau^{2}} =0 \implies \frac{d}{d\tau} (a-bu-e^{ -u }) = \frac{du}{d\tau}(e^{ -u } -b)=0
$$
Which tells us that the critical points of $du /d\tau$ occur when $du /d\tau$ itself is 0, or when $u=\ln(1 /b)$. The first case corresponds with the roots of $du /d\tau$, and so the non-zero extrema of $du /d\tau$ occur exclusively in the second case.

At $t=0$, assume $R(t)=0$ and so $u=0$.
$$
	\frac{d^{2}u}{d\tau^{2}} \bigg|_{t=0} = (a-0-e^{ 0 })(e^{ 0 }-b) = (a-1)(1-b)
$$
Which is positive under the condition $b< 1$. Furthermore, under these same conditions:
$$
	\frac{du}{d\tau} \bigg|_{t=0} = \frac{du}{d\tau} \bigg|_{u=0} = a-1 \geq 0
$$
I conclude that, in the case when $b<1$, at $t=0$, $u$ begins at 0 with a non-negative increasing derivative. $\dot{u}$ then reaches a maximum at some time $t_\text{peak}$ that corresponds with $u=\ln(1 /b)>0$.

Additionally, as established in part f, there is a stable fixed point $\dot{u}=0$ at $u>0$. After being repelled by the unstable fixed point, $\dot{u}$ will eventually decay to 0 at this fixed point.

---
i.
By the same logic used in part h,
$$
	\frac{d^{2}u}{d\tau^{2}} \bigg|_{t=0} = (a-1)(1-b) <0
$$
In the case when $b>1$. Additionally, $\ln(1 /b)<0$. Unlike the previous case, starting at $t=0$, $\dot{u}$ is always decreasing for $t>0$. This means that the severity of the disease will never increase, and so $t_\text{peak}=0$.

---
j.
$b$ is the ratio between the disease spread rate and the removed rate. When $b>1$, people are either recovering or dying faster than the sickness can spread. On the other hand, $b<1$ means that the illness is spreading faster than people can recover or die.

---
k.
For Covid-19, the spread rate would be very high in comparison to the removal rate. Furthermore, the model may have to account for the rapid mutations in the disease. Somebody immune to an older version of Covid-19 is not necessarily immune to newer strains.

For HIV, both the spread rate and removal rate would be quite small, since it is such a slow acting disease. So slow, in fact, that it may be necessary to account for population growth in the model.