Today we will begin our discussion of Amortized Analysis.

Intuitively, the amortized cost per operation is simply the average cost. That is, $T(n)$ is the maximum cost of performing any sequence of $n$ operations. Where we call $T(n) /n$ the amortized cost per operation.

In this course, we will compute the amortized cost with *aggregate analysis*, and the *accounting method*.
# Aggregate Analysis
Imagine we have some counter with $k$ bits, and we would like to increment it by one. Notice that the number of bits we flip will change depending on the current number.

It is possible, for example, to just flip one bit before carrying on. However, it is also possible that a single increment will chain onto numerous '1's, thus resulting in more bits being flipped.

To establish a trivial upper-bound, note that each increment can flip at most $k$ bits. Then,
$$
	T(n) = nk \implies \frac{T(n)}{n}=k
$$
But we can do better than this. We will use aggregate analysis.

Say we have some 4 bit number we are incrementing:
![[Pasted image 20261019215755.png]]
The 0th bit increments every increment, the 1st every 2, the 2nd every 4. So the number of flips for the $i$th bit is $2^i$ times. All the way up to the $k-1$th bit. The total number of bit flips is therefore,
$$
	T(n) = \sum_{i=0}^{k-1} \left\lfloor  \frac{n}{2^i}  \right\rfloor < n \sum_{i=0}^{\infty} \frac{1}{2^i} = 2n
$$
The amortized cost is therefore:
$$
	\frac{T(n)}{n} < 2 \in O(1)
$$
# Accounting Method
This method uses charge and credit as a metaphor to visualize running costs.

Each operation is charged to cover some "actual cost." The charge of an operation may exceed the actual cost. This excess is saved as credit, which can be assigned to other operations. A later operation can then use these saved credits to cover part of its actual cost.
- Basically some operations will use more, and some operations will use less. Imagine their running costs as a bar graph. Cut off the tops of the tallest bars, and fit them inside the shorter ones. That is the charge and credit metaphor

We require that the total charges on any prefix of operations must be $\geq$ the total cost of the operations. This amount we choose to charge is $\geq$ the amortized cost.

More precisely, for the $i$th operation in a sequence, if $c_{i}$ is the actual cost, and $\hat{c}_{i}$ is the charged amount, then we require:
$$
	\sum_{i=1}^{k} \hat{c}_{i} \geq  \sum_{i=1}^{k} c_{i}
$$
After every prefix of $k$ operations.

Going back to our example with the incrementing number, note that there are two things are have a cost:
1. Setting one bit $0\to1$
2. Resetting a bit $1\to 0$

Our plan will be to charge \$2. So that \$1 may be used to cover the cost of the $0\to 1$ bit flip, and the extra credit will be used to reset that same bit later on.
- It sounds like it would be challenging to come up with a charge without having analyzed the system prior

One may visualize the cost like so:
![[Pasted image 20261019222930.png]]
Or alternatively, with a larger number:
![[Pasted image 20261019222944.png]]
Notice that the actual cost of \$6 is covered as follows:
1. \$5 collected from the credit of each 1
2. \$1 taken from the charge.
The \$1 credit we are left with is attached to the new 1, to reset it later.

Since the total number of accumulated credits is $\geq$ the total number of 1s in the counter, we have found a valid charge.

The amortized cost is therefore $2\in O(1)$.
