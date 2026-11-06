Today we will expand on our discussion of amortized complexity.
# Example 1
We will use the accounting method to implement a queue build from two stacks.

To implement this we will use one stack for enqueues, and one for dequeues. Whenever we enqueue something, we push it into the first stack. When we dequeue, we empty out stack 1, and fill up stack 2. Then we pop the last element.

It works something like this:
Enqueue(x)
```
stk1.push(x)
```

Dequeue(x)
```
if stk2 is empty
	while stk1 is not empty
		stk2.push(stk1.pop())
return stk2.pop()
```

Lets analyze this with the accounting method.

The cost for each enqueue is trivially 1. But to dequeue, it is $2n+1$, where $n$ is the size of stack 1. Notice that this is the case only if stack 2 is empty, otherwise, it is constant.

Upon an enqueue, we charge 3 to push, and 2 to move it over from one stack to the other. Afterwards, we'll pay for the final pop with 1.

We would like to show that for every sequence of $m$ starting from an empty queue, every element in stack 1 is charged 2, and the total charge $\geq$ total cost.

We will prove this with induction.

Base case: $m=0$. Which is trivially true, there are no operations.

Inductive step: Suppose the claim is true for $m$ operations, show that it is true after any $m+1$ operation.

With our accounting scheme, this is how the two possible cases look:

If we enqueue, we provide 1 to push, and store 2 in $x$. This satisfies our conditions.

If we dequeue there are two subcases:
- If stack 2 is not empty, stack 1 remains unchanged, and we pay for the pop with our charge of 1
- If stack 2 is empty, then, by the induction hypothesis, every element in stack 1 can pay for its move to stack 2. Then, we pay for the final pop with 1. Stack 1 is also empty, so the conditions are maintained.

So, when we enqueue, we cover our costs by providing 3, and 1 when we dequeue. So the amortized cost per operation is $3m /m=3\in O(1)$.
# Example 2
Consider an unsorted linked list $L$. Track the length of $L$ in $n$ support operations.

It has the following operations:

Insert(x)
```
Append x to the end of L
Increment n
```

Diminish()
```
m = Median(L)
Loop over all elements
	Remove if >= m
	Do nothing otherwise
Add back copies of m to length is floor(n/2)
n = floor(n/2)
```
Diminish is essentially trying to remove the $\lceil n /2 \rceil$ largest values in $L$. The median is the $\lceil n /2 \rceil$ largest element. We assume that it can be found within $5n$ operations.

Note that the cost for an insertion is 0, but the cost for a diminish is $6n$. We will charge 12 on insert, and 0 on diminish.

Now, we would like to prove:
1. Each element in $L$ has 12
2. Total charge $\geq$ total cost

Base case: $m=0$. Trivially true again.

Inductive step: Assume it holds after $m$ steps, prove that it holds after $m+1$.

Insert cost 0, so we have charged enough. The new element has been given 12, so both statements have been proven.

To diminish, we use the credit in the $\lceil n /2 \rceil$ removed elements to pay for the $6n$ cost.
$$
	12 \lceil n /2 \rceil \geq  12 \frac{n}{2} = 6n
$$
So we have successfully paid for the operations. Furthermore, the remaining elements are untouched, and so we have validated both statements.
- Intuitively, what is going on here is that 6 from the insert is used to pay for itself, and another 6 is used to pay for somebody else's operation. As a result, everybody has enough.

The amortized cost is therefore:
$$
	\frac{12m}{m} = 12 \in O(1)
$$
