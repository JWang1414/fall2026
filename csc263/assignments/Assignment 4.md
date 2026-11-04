# Question 1
---
a.
There are $k$ empty slots in $T$, which has $m$ slots in total. The possibility that $x$ is hashed into an empty slot by $h_{1}$ is $k /m$. The chance is the same for $h_{2}$, since they are independent from each other.

The total chance that $x$ is inserted into an empty slot is the chance that $T[h_{1}(x)]$ or $T[h_{2}(x)]$ is an empty slot.
$$
	\begin{align}
	P(\text{empty}\cup\text{empty}) & = P(\text{empty}) + P(\text{empty}) - P(\text{both empty}) \\
	 & = \frac{k}{m} + \frac{k}{m} - \frac{k}{m} \frac{k}{m} \\
	 & = \frac{2k}{m} - \left( \frac{k}{m} \right)^{2}
	\end{align}
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
To compute the probability of returning True, I will instead compute the probability it will return False. At every iteration, the chance that $A[i]$ is not $x$ is:
$$
	1-\frac{k}{n} = \frac{n-k}{n}
$$
This algorithm will loop $r$ times. If $i$ is always chosen uniformly with replacement, and each loop is independent from each other, than the chance that this algorithm returns False after $r$ iterations is:
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
My solution will use the forest structure, with the weighted union heuristic, and path compression.

Begin by defining $n$ distinct sets $x_{1}, x_{2}, \dots, x_{n}$, where each value $x_{i}$ is a pointer to the $i$th element in the array $A$ of size $n$. Create the new empty list $Q$ of (currently) 0 constraints. Then, loop through the list $L$ of $m>n$ constraints.
1. Upon encountering an equality constraint, merge the two sets containing $x_{i}$ and $x_{j}$. That is, Union($x_{i}, x_{j}$).
2. Upon encountering an inequality constraint, append it to $Q$.

When all the constraints of $L$ have been seen, begin looping through $Q$, which will contain exclusively inequality constraints. For each inequality constraint, check if $x_{i}$ and $x_{j}$ are in the same set. If so, then return nil, because $L$ is not satisfiable. That is, if $\text{Find}(x_{i})=\text{Find}(x_{j})$, return nil. Otherwise output the array $A[1\dots n]$.

To make $A$, the values in each set should be set to the same value. If we for example have the sets $\{ A[1], A[2] \}, \{ A[3], A[4] \}, \{ A[5] \}$, then we would expect $A[1]=A[2]=1$, $A[3]=A[4]=2$, and $A[5]=3$.

I will construct $A$ as a direct access array of size $n$. Define the variable $k=1$, which will help define the values in $A$.
1. Run Find($x_{1}$) to determine the head/representative of this tree $h$
2. If $h$ is currently undefined, set $x_{1}$ and $h$ to $k$, and increment $k$ by 1. Otherwise, set $x_{1}=h$.
3. Repeat the same steps for $x_{2}\dots x_{n}$.
---
b.
is_satisfiable(n, L)
```
A = direct access array of size n. All values initially 0.
x = Set containing disjoint sets {A[i]} from 1 to n.

Q = []
for constraint in L:
	if equality constraint x[i] = x[j]:
		Union(x[i], x[j])
	else:
		Q.append(constraint)

for constraint in Q:
	if Find(x[i]) = Find(x[j]):
		return nil

k = 1
for i = 1...n:
	if A[i] == 0:
		h = Find(x[i])
		if h.value = 0:
			h.value = k
			A[i] = k
			k += 1
		else:
			A[i] = h.value
return A
```
---
c.
Assuming all variables can be declared in $O(1)$ time, there are three main sub-segments of my algorithm: building a queue for the constraints, checking if the constraints are valid, and constructing $A$.

To build a queue for the constraints, all elements of $L$ are looped over. For each of the $m$ elements, two sets $x_{i}$ and $x_{j}$ are Union'd, or a constraint is added to the queue $Q$. Both operations take constant time. It therefore takes $O(m)$ time to build a queue for the constraints.

To check if the constraints are valid, all elements of $Q$ are looped over. The maximum length of $Q$ is $m$. For each element in $Q$, there are two Finds. According to the theorem from lecture 12, with WU and PC, executing a sequence of $n-1$ Unions and $m\geq n$ Finds will take $O(m\log^*n)$ time. In this loop, there are 0 Unions, but $2m$ Finds. The runtime of this segment is therefore $O(2m\log^*n)$ or $O(m\log^*n)$.

To construct $A$, a loop is defined to run from 1 to $n$, the size of $A$. This segment therefore completes in $O(n)$ time.

The total runtime is therefore:
$$
	O(m) + O(m\log^*n) + O(n) \implies O(m\log^*n)
$$
