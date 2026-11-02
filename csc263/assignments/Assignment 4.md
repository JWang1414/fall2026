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
---
a.
There are $k$ copies of $x$ in $A[1\dots n]$. $n$ is the size of $A$. Since the index $i$ is chosen uniformly at random, the chance of finding $x$ in one try will be $k /n$.

---
b.
To compute the probability of returning True, I will instead compute the probability it will return False. At every iteration, the chance that $A[i]$ is not $x$ is $(n-k) /n$. This algorithm will loop $r$ times. If $i$ is always chosen uniformly with replacement, and each loop is independent from each other, than the chance that this algorithm returns False after $r$ iterations is:
$$
	\left( \frac{n-k}{n} \right)^{r}
$$
The probability that it will return True is therefore:
$$
	1-\left( \frac{n-k}{n} \right)^{r}
$$
---
c.
The chance that the algorithm returns True after exactly $r$ iterations is:
$$
	\left( \frac{n-k}{n} \right)^{r-1}\left( \frac{k}{n} \right)
$$
The expected number of loop iterations is:
$$
	E(R) = \sum rP(R=r) = \sum_{r=1}^{\infty} r \left( \frac{n-k}{n} \right)^{r-1}\left( \frac{k}{n} \right)
$$
Define the new variable $a=r-1\implies r=a+1$ to shift the indices,
$$
	= \frac{k}{n} \sum_{a=0}^{\infty} (a+1) \left( \frac{n-k}{n} \right)^{a} \propto 
	\sum_{a=0}^{\infty} a\left( \frac{n-k}{n} \right)^{a} + \sum_{a=0}^{\infty} \left( \frac{n-k}{n} \right)^{a}
$$
Apply the following series identities (the first is just the geometric series):
$$
	\sum_{k=0}^{\infty} x^{k} = \frac{1}{1-x} \qquad \sum_{k=0}^{\infty} kx^{k} = \frac{x}{(x-1)^{2}}
$$
Then,
$$
	\sum_{a=0}^{\infty} a\left( \frac{n-k}{n} \right)^{a} + \sum_{a=0}^{\infty} \left( \frac{n-k}{n} \right)^{a} = \frac{n(n-k)}{k^{2}} + \frac{n}{k}
$$
So the expected number of loops is:
$$
	\frac{k}{n} \left( \frac{n(n-k)}{k^{2}} + \frac{n}{k} \right) = \frac{n}{k}
$$
# Question 3
---
a.
