# Question 1
---
a.
There are $k$ empty slots in $T$, which has $m$ slots in total. The possibility that $x$ is hashed into an empty slot by $h_{1}$ is $k /m$. The chance is the same for $h_{2}$, since they are independent from each other.

The total chance that $x$ is inserted into an empty slot is the chance that $T[h_{1}(x)]$ or $T[h_{2}(x)]$ is an empty slot.
$$
	P(\text{empty}) + P(\text{empty}) - P(\text{both empty}) = \frac{k}{m} + \frac{k}{m} - \frac{k}{m} \frac{k}{m} = \frac{2k}{m} - \left( \frac{k}{m} \right)^{2}
$$
---
b.
