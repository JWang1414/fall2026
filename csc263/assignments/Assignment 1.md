# Question 1
Rough work:
$$
	A[n-j+1] = j-1
$$
$$
	A[n-1+1] = 1-1 \implies A[n]=0
$$
$$
	A[n-2+1] = 2-1 \implies A[n-1]=1
$$
$$
	A[n-n+1] = n-1 \implies A[1] = n-1
$$
$$
	A[n-(n-1)+1] = (n-1)-1 = A[n-n+1+1] = A[2] = n-2
$$
$$
	A[n] + A[1] = 0 + n-1=n-1
$$
$$
	A = \{ n, n-2, n-3, \dots, 2, 1, 0 \}
$$
---
Want to show that the time complexity $T(n)$ is $\Theta(n)$.

Lemma. For an array $A$ of size $n$, $A[n-i+1]=i-1\implies A[n]+A[1]=n-1$. Where $i\in \mathbb{N}$ in $[1, n]$.

Define an array of size $n$. Assume that the elements of this array are defined such that $A[n-i+1]=i-1$, where $i\in \mathbb{N}$ in $[1, n]$.

When $i=1$,
$$
	A[n-1+1] = 1-1 \implies A[n]=0
$$
When $i=n$,
$$
	A[n-n+1] = n-1 \implies A[1] = n-1
$$
Therefore,
$$
	A[n] + A[1] = 0 + (n-1) = n-1
$$
As needed.

Show $\Omega(n)$.

Define an array $A$ of size $n$ such that the elements are $A[n-i+1]=i-1$. Note that this is the negation of the condition inside the inner loop. The inner loop will therefore run to completion, iterating $n$ times.

By the lemma, $A[n]+A[1]=n-1$. The condition in the outer loop is fulfilled, and the loop terminates in constant time.

Since the outer loop will always terminate, $T(n)$ is at least $n$. FREAK is therefore $\Omega(n)$.

Show $O(n)$.
- Split this one into cases

Define an array $A$ of size $n$, $j\in \mathbb{N}$ such that $0<j\leq n$.

Case 1: For all $j$, $A[n-j+1]=j-1$

By the lemma, this also necessitates that $A[n]+A[1]=n-1$. Forcing the outer loop to terminate after running one time. For the same reasons FREAK is $\Omega(n)$, the maximum number of iterations is $n+\text{constant}$.

Case 2: For at least one $j$, $A[n-j+1]\neq j-1$

Then the inner loop, and consequently the function, will terminate in $\leq n$ iterations, without ever making it to the outer loop.

The maximum number of iterations in FREAK is therefore $n$ in the inner loop, and some constant outside this loop. Therefore, FREAK is $O(n)$.

Since FREAK is $\Omega(n)$ and $O(n)$, FREAK is $\Theta(n)$, as needed.
# Question 2
Rough work.

I will use a max-heap to solve this problem. My algorithm will save exclusively the smallest keys that will be printed. Any other larger numbers will not be saved.

To print out the max-heap, simply loop through the entire array and print out every element. Since the heap contains only the smallest keys, it will have size $m$ at maximum. Worst-case runtime is $O(m)$.

To process a new key input:
1. Check if the input is less than the maximum in the heap. Getting the max from a max-heap is $O(1)$, and the single comparison is also constant time. Total complexity $O(1)$.
2. If the input is smaller, replace the max value with the input. This is a single operation, and so trivially $O(1)$.
3. Re-arrange the resulting heap to maintain the max-heap properties. In an identical manner to the insert and extract_max operations, the input value will, at most, shift from the top of the heap to the bottom. The height of the heap is $\lfloor \log_{2}m \rfloor$. So the runtime is $O(\log m)$.
---
Pseudo-code.
`PRINT_OPERATION(A[1..m])`
```
for key in A[1..m]
	print key
```

`PROCESS_INPUT(input)`
```
if input >= A.max then return
A[1] = input

i = 1
while 2i <= A.size
	// If the input is larger than its children, terminate
	if A[2i+1] exists and A[i] >= max(A[2i], A[2i+1]) then return

	// Swap the input with the larger child
	if A[2i+1] doesn't exist or (A[2i] > A[2i+1] and A[i] < A[2i]) then
		A[i], A[2i] = A[2i], A[i]
		i = 2i
	elif (A[2i] < A[2i+1] and A[i] < A[2i+1]) then
		A[i], A[2i+1] = A[2i+1], A[i]
		i = 2i+1
```
---
Proof of correctness

Want to show that $A$ always contains the $m$ smallest keys.

Proof by induction.

Base case: $m=1$

Suppose the algorithm has been given a single value that has been saved in $A$. If $n$ is the key saved in $A$, then $n$ is trivially the smallest value. If another value $a$ is an input, and $a<n$, then $n$ is replaced with $a$. Otherwise, $a$ is discarded. In all cases, $n$ remains the smallest number input to the algorithm, while also remaining a valid max-heap.

During a PRINT operation, the smallest number is printed.

Inductive step. Want to show that if $A$ can contain $m$ correct keys, then $A$ can contain $m+1$ correct keys.

For any given max-heap with a finite size, another entry can be inserted at the end of the heap before being properly organized in the array. The addition of this new entry does not violate the max-heap principles.

In the context of this algorithm, it means that if the max-heap properties are maintained for a heap of size $m$, then it will also be upheld for a heap of size $m+1$. Furthermore, if the input value is smaller than the max value in the heap, then it is replaced by the input value. Therefore, this algorithm will always maintain the $m+1$ smallest keys within a valid max-heap, so long as it also does so for $m$ entries.

If a PRINT operation yields the $m$ smallest keys, then it may also yield the $m+1$ smallest keys.

- This, in combination with the base case should be enough to prove correctness
