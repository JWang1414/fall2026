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