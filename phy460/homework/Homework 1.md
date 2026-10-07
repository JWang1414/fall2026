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
$$
	\dot{x}=1+rx+x^{2}
$$
- Adjusting the value of $r$ reveals that there are two possible saddle-node bifurcations
$$
	\dot{x}=r-\cosh x \implies r=\cosh(x)
$$
- Another saddle-node bifurcation. This time there's just one
- They join together when $r=1$
$$
	\dot{x}=r^{2}-x^{2} \implies (r+x)(r-x)=0
$$
- There is a saddle-node bifurcation at $x=0$ and $r=0$. However, it does not disappear. It is originally two fixed points, merges into one, and then splits into two again
$$
	\dot{x}=x(r-e^{ x }) \implies x=0, r=e^{ x }
$$
- Little stranger. I think these are still saddle node bifurcations. The stability of the two bifurcations swap
- The bifurcation graph seems to look like a logarithmic graph
- I tried to use arrows to indicate stability on the axis
$$
	\dot{x}=rx-\ln(1+x) \implies rx=\ln(1+x)
$$
- Very similar to the last one, but the logarithmic bifurcation line is flipped upside-down
$$
	\dot{x} = x+\tanh(rx) \implies -x=\tanh(rx)
$$
- This one is a subcritical pitchfork bifurcation
$$
	\dot{x} = rx+ \frac{x^{3}}{1+x^{2}} \implies -rx=\frac{x^{3}}{1+x^{2}}
$$
- Another subcritical pitchfork bifurcation
# Question 5
$$
	\dot{\theta} = \sin ^{3}\theta
$$
- This one is quite simple, it's perfectly periodic on the $2\pi$ scale
- It has 2 fixed points, be careful about the one at the ends. That really represents just one fixed point
$$
	\dot{\theta} = \sin\theta + \cos\theta
$$
- Amplitude is a little bigger
- Has 2 fixed points
- Interval looks a little weird
$$
	\dot{\theta} = \sin(k\theta)
$$
- The number of fixed points depends on $k$
- Otherwise, relatively normal. Amplitude is 1, $k$ just changes the oscillation speed
# Question 6
$$
	\dot{\theta} = \frac{\sin \theta}{\mu+\cos \theta}
$$
The fixed points show up at predictable locations $\sin\theta=0$. That is, the fixed points are always located at 0 and $\pi$.

The denominator determine the behaviour of this vector field, and is how bifurcations occur. It is only when $\mu+\cos \theta$ is well defined that the vector field as a whole is well defined.

- Are the asymptotes classified as fixed points? I don't know

Case $k<-1$ or $k>1$
- There are 3 well defined fixed points

Case $k=-1$
- The fixed point at $\theta=0$ disappears, it is replaced with an asymptote
- There is just one remaining fixed point at $\theta=\pi$

Case $-1<k<1$
- The two fixed points $\theta=0, \pi$ remain intact
- There are two asymptotes between the fixed points

Case $k=1$
- The fixed point at $\theta=\pi$ disappears, replaced with an asymptote
- There is just one remaining fixed point at $\theta=0$

$$
	\dot{\theta} = \mu+\sin\theta + \cos(2\theta)
$$
Bifurcations occur at $\theta=1.125, 0, 2$.

At $\theta=1.125$ there are two saddle node bifurcations that split from each other. There are two fixed points in total

As a result, when $1.125<\theta<0$ there are 4 fixed points

At $\theta=0$ two of two fixed points merge together and disappear. There are three fixed points in total

When $0<\theta<2$ there are two fixed points remaining from the two saddle nodes

At $\theta=2$ they merge into one fixed point.

In all other regions there are 0 fixed points
# Question 3
---
a.
$N$ is constant means that $\dot{N}=0$. Want to show that:
$$
	\dot{S}+\dot{I} + \dot{R}=0
$$
Equivalent to:
$$
	-\beta SI + \left[ \beta SI - \alpha I \right]  + \alpha I = -\beta SI + \beta SI - \alpha I  + \alpha I =0
$$
As needed.

---
b.
$$
	\dot{R} = \alpha I \implies I = \frac{\dot{R}}{\alpha}
$$
Sub into $\dot{S}$
$$
	\dot{S} = -\beta S\left( \frac{\dot{R}}{\alpha} \right) = -\frac{\beta}{\alpha} S\dot{R}
$$
$$
	\frac{dS}{dt}=-\frac{\beta}{\alpha} S \frac{dR}{dt} \implies \frac{dS}{S}=-\frac{\beta}{\alpha} \frac{dR}{dt} dt
$$
Integrate both sides
$$
	\int_{S_{0}}^{S} \frac{1}{S} \, dS = \ln S - \ln S_{0}
$$
$$
	\int -\frac{\beta}{\alpha} \, dR = -\frac{\beta}{\alpha}R
$$
Equate the two and re-arrange,
$$
	\ln S = -\frac{\beta}{\alpha}R + \ln S_{0} \implies S = e^{ -\beta R/\alpha + \ln S_{0} } = e^{ \ln S_{0} } e^{ -\beta R/\alpha }
$$
$$
	S(t) = S_{0}\exp\left( -\frac{\beta}{\alpha}R(t) \right)
$$
As needed.

---
c.
$$
	S+I+R=N \implies I = N-S-R
$$
$$
	= N-R-S_{0}\exp\left( -\frac{\beta}{\alpha} R(t) \right)
$$
Therefore,
$$
	\dot{R}=\alpha I = \alpha \left[ N-R-S_{0}\exp\left( -\frac{\beta}{\alpha} R(t) \right) \right]
$$
---
d.
$$
	\alpha=l \qquad R=z \qquad S_{0}=x_{0} \qquad \beta=k
$$
$$
	u=\frac{kz}{l} \qquad \tau = kx_{0}t \qquad a=\frac{N}{x_{0}} \qquad b=\frac{l}{kx_{0}}
$$
$$
	u=\frac{\beta}{\alpha}R(t) \qquad \tau= \beta S_{0}t \qquad a=\frac{N}{S_{0}} \qquad b=\frac{\alpha}{\beta S_{0}}
$$
Substituting in $u$ we have:
$$
	\frac{dR}{dt} = \alpha \left( N - \frac{\alpha}{\beta}u - S_{0}e^{ -u } \right) = \alpha S_{0} \left( \frac{N}{S_{0}} - \frac{\alpha}{\beta S_{0}}u - e^{ -u } \right)
$$
$$
	\frac{1}{\alpha S_{0}} \frac{dR}{dt} = a-bu-e^{ -u }
$$
Left-side:
$$
	\frac{du}{dt} = \frac{\beta}{\alpha} \frac{dR}{dt} \implies \frac{dR}{dt} = \frac{\alpha}{\beta} \frac{du}{dt}
$$
$$
	\frac{1}{\alpha S_{0}} \frac{dR}{dt} = \frac{1}{\alpha S_{0}} \frac{\alpha}{\beta} \frac{du}{dt} = \frac{1}{\beta S_{0}} \frac{du}{dt} = \frac{du}{d\tau}
$$
Therefore:
$$
	\frac{du}{d\tau} = a-bu-e^{ u }
$$
As needed.

---
e.
Note that:
$$
	a=\frac{N}{S_{0}} \qquad b=\frac{\alpha}{\beta S_{0}}
$$
Note that $S$, $I$, $R$, $S_{0}$ are necessarily positive to have physical meaning. Additionally, recall that $\alpha$ and $\beta$ are both defined as positive constants. $b$ must therefore also be a positive constant $b>0$.

At $t=0$,
$$
	a=\frac{N}{S_{0}} = \frac{S_{0}+I(0)+R(0)}{S_{0}} \geq 1
$$

---
f.
$$
	a-bu-e^{ -u } =0 \implies a-bu = e^{ -u }
$$
Since $a\geq 1$ and $b> 0$, this function will have 1-2 fixed points.

Case: Single fixed point
- Negative, semi-stable fixed point
- Occurs at $u=0$ when $a=1$ and $b=1$

Case: Two fixed points, $b>1$
- Unstable fixed point $u<0$ and stable fixed point $u>0$

Case: Two fixed points, $b<1$
- Unstable fixed point $u<0$ and stable fixed point $u>0$
---
g.
Recall from the definition of $u$ we have:
$$
	u(t) = \frac{\beta}{\alpha}R(t)
$$
Compute the first derivative:
$$
	\dot{u} = \frac{\beta}{\alpha}\dot{R} = \beta I =0
$$
Note that $\dot{u}$ is proportional to $\dot{R}$ and $I$. So their maximums will occur at the same time. The maximum of $u'(\tau)$ occurs when:
$$
	u''(\tau) =0 \implies \frac{d}{d\tau} \frac{du}{d\tau} = \frac{d}{d\tau} (a-bu-e^{ -u }) = -b \frac{du}{d\tau} + e^{ -u } \frac{du}{d\tau} = \frac{du}{d\tau}(e^{ -u }-b) =0
$$
So when $du /d\tau=0$ or $u=\ln(1 /b)$.

---
h.
I will use $du /d\tau$ to determine the behaviour of $\dot{u}$ at $t=0$. The critical points of $du /d\tau$ will occur when:
$$
	\frac{d^{2}u}{d\tau^{2}} =0 \implies \frac{d}{d\tau} (a-bu-e^{ -u }) = \frac{du}{d\tau}(e^{ -u } -b)=0
$$
Which tells us that the critical points of $du /d\tau$ occur when $du /d\tau$ itself is 0, or when $u=\ln(1 /b)$. The first case corresponds with the roots of $du /d\tau$, and so the non-zero extrema of $du /d\tau$ occur exclusively in the second case.

At $t=0$, $R(t)\approx 0\implies u\approx0$. So,
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
In the case when $b>1$. Additionally, $\ln(1 /b)<0$. Unlike the previous case, starting at $t=0$, $\dot{u}$ is an always decreasing function, with a maximum that occurs at a non-physical state. This means that the severity of the disease will never increase, and so $t_\text{peak}=0$.

---
j.
$b$ is the ratio between the disease spread rate and the removed rate. When $b>1$, people are either recovering or dying faster than the sickness can spread. On the other hand, $b<1$ means that the illness is spreading faster than people can recover or die.

---
k.
For Covid-19, the spread rate would be very high in comparison to the removal rate. Furthermore, the model may have to account for the rapid mutations in the disease. Somebody immune to an older version of Covid-19 is not necessarily immune to newer strains.

For HIV, both the spread rate and removal rate would be quite small, since it is such a slow acting disease. So slow, in fact, that it may be necessary to account for population growth in the model.