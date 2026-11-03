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
My solution will use the forest structure, with the weighted union heuristic, and path compression.

Begin by defining $n$ distinct sets $x_{1}, x_{2}, \dots, x_{n}$, where each value $x_{i}$ is a pointer to the $i$th element in the array $A$ of size $n$. Create the new empty list $Q$ of (currently) 0 constraints. Then, loop through the list $L$ of $m<n$ constraints.
1. Upon encountering an equality constraint, merge the two sets containing $x_{i}$ and $x_{j}$. That is, Union($x_{i}, x_{j}$).
2. Upon encountering an inequality constraint, append it to $Q$.

When all the constraints of $L$ have been seen, begin looping through $Q$, which will contain exclusively inequality constraints. For each inequality constraint, check if $x_{i}$ and $x_{j}$ are in the same set. If so, then return nil, because $L$ is not satisfiable. That is, if $\text{Find}(x_{i})=\text{Find}(x_{j})$, then return nil. Otherwise output the array $A[1\dots n]$.

To make $A$, the values in each set should be set to the same value. If we for example have the sets $\{ 1, 2 \}, \{ 3, 4 \}, \{ 5 \}$. Then we would expect to have $x_{1}=x_{2}=1$, $x_{3}=x_{4}=2$, and $x_{5}=3$.

$A$ can be constructed with a direct access array of size $n$.
1. Run Find($x_{1}$) to determine the head/representative of this tree $h$
2. Recursively search through all the children of $h$, setting each associated value in $A$ to 1
3. After going through every value in this tree, repeat these steps for the next vacant spot in $A$. This time, setting the associated values to 2, and so on.
---
b.
isSatisfiable(n, L)
```
A = direct access array of size n. All values initially 0.
S = Set containing disjoint sets {x_i} from 1 to n

# Organize the list of constraints
Q = []
for constraint in L:
	if equality constraint x_i = x_j:
		Union(x_i, x_j)
	else:
		Q.append(constraint)

# Check if the constraints are valid
for constraint in Q:
	if Find(x_i) = Find(x_j):
		return nil

# Construct A
k = 1
for i = 1 to n:
	if A[i] == 0:
		root = Find(S[i])
		fillTree(root, k)
		k += 1

return A
```

fillTree(node, k)
```
node.value = k
for child in node.children:
	fillTree(child)
```
---
c.
Assuming all variables can be declared in $O(1)$ time, there are three main segments of my algorithm: building a queue for the constraints, checking if the constraints are valid, and constructing $A$.

To build a queue for the constraints, all elements of $L$ are looped over. For each of the $m$ elements, two sets $x_{i}$ and $x_{j}$ are Union'd, or a constraint is added to the queue $Q$. Both operations take constant time. It therefore takes $O(m)$ time to build a queue for the constraints.

To check if the constraints are valid, all elements of $Q$ are looped over. The maximum length of $Q$ is $m$. For each element in $Q$, there are two Finds. According to the theorem from lecture 12, with WU and PC, executing a sequence of $n-1$ Unions and $m\geq n$ Finds will take $O(m\log^*n)$ time. In this loop, there are 0 Unions, but $2m$ Finds. The runtime of this segment is therefore $O(2m\log^*n)$ or $O(m\log^*n)$.

To construct $A$, all values in $A$ must be traveled to. $A$ is an array of size $n$, and so this sub-algorithm will take $O(n)$ time.

The total runtime is therefore:
$$
	O(m) + O(m\log^*n) + O(n) \implies O(m\log^*n)
$$