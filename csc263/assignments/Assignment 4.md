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
Definition of the expectation value:
$$
	E(X) = \sum xP(X=x)
$$
Where $X$ denotes an event, and $x$ is some outcome.

(I drew a table of all the possibilities, since $m$ is small.)

The total number of possibilities is $m^{2}=16$. Define $P(l=n)$ as the probability $P$ that the length $l$ is $n$ elements long. There are three possibilities with the following probabilities:
$$
	P(l=3) = \frac{7}{16} \qquad P(l=4) = \frac{5}{16} \qquad P(l=9) = \frac{4}{16}
$$
According to the definition of the expectation value, the expected length of the chain is:
$$
	E(l) = 3\left( \frac{7}{16} \right) + 4\left( \frac{5}{16} \right) + 9\left( \frac{4}{16} \right) = \frac{77}{16} = 4.8125
$$
# Question 2
