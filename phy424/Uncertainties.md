# General uncertainties
If $y$ is a measurand and $x_{1}, x_{2}, \dots, x_{n}$ are input values with uncertainties $u(x_{1}), u(x_{2}),\dots, u(x_{n})$ then uncertainty $u(y)$ is calculated according to:
$$
u(y) = \sqrt{ \left( \frac{ \partial y }{ \partial x_{1} }  \right)^2(u(x_{1}))^2 + \left( \frac{ \partial y }{ \partial x_{2} }  \right)^2(u(x_{2}))^2 + \dots + \left( \frac{ \partial y }{ \partial x_{n} }  \right)^2(u(x_{n}))^2}
$$
# Type A and B uncertainties
If both type A and type B uncertainties are present the total uncertainty can be calculated using: $$
u(x) = \sqrt{ u(x)^2_{A} + u(x)^2_{B} + 2u(x)_{A}u(x)_{B} }
$$
For most measurements, type A and B uncertainties are independent, therefore
$$
u(x)_{A}u(x)_{B} = 0
$$
Uncertainty can be then calculated as
$$
u(x) = \sqrt{ u(x)^2_{A} + u(x)^2_{B} }
$$
# Common uncertainties
1. $f = x\pm y\implies u(f) = \sqrt{ u(x)^2+u(y)^2 }$
2. $f=xy\vee f=\frac{x}{y}\implies u(f) = f\sqrt{ \left( \frac{u(x)}{x} \right)^2 + \left( \frac{u(y)}{y} \right)^2 }$
3. $f=nx$ where $n=\text{constant}$ and $u(n)=0$ then $u(f)=n*u(x)$
4. $f=x^n$ where $n=\text{constant}$ and $u(n)=0$ then $u(f) = n*f*\frac{u(x)}{x}$
# Standard error
If there are $n$ values of a quantity, $x_{1},x_{2}, \dots, x_{n}$, the standard deviation, $\sigma$, of these $n$ values is given by:
$$
\sigma = \sqrt{ \frac{1}{n-1} \left( \sum^n_{i=1}(x_{i}-\bar{x})^2 \right) }
$$
$\bar{x}$ is the mean of the measurements, defined as:
$$
\bar{x} = \frac{1}{n}\sum^n_{i=1}x_{i}
$$
The standard uncertainty, $u(\bar{x})$, of the mean $\bar{x}$ is less than the standard deviation if the values are uncorrelated. It can be calculated as:
$$
u(\bar{x}) = \frac{\sigma}{\sqrt{ n }}
$$
