Today, we continue our discussion of amortized cost. Today we will investigate a dynamic table.

The dynamic table is some table $T$, with Insert and Delete operations. Define the load factor:
$$
	\alpha(T) = \frac{\text{Num. items in }T}{\text{size}(T)}
$$
So, when $\alpha=1$, we can no longer put anything in the table. In this case, we must expand the table. To expand the table, we may either double or halve its size.

The dynamic table will be used to represent some amount of memory.

Each Insert and Delete will cost 1. And an expansion costs $n$, where $n$ is the number of slots the table has gained.
# Insertions
Now, say we begin with a table of size 1, and we would like to insert $n=25$ items into the table.

When doing aggregate analysis, one can see that the cost of insertion is trivially 25. Now, we must double the size of the table until it has size 32. The total cost is therefore:
$$
	25+1+2+4+8+16
$$
Notice that the expansion terms are all powers of two $\leq 25$.
$$
	n + \sum_{k=0}^{\log n} 2^{k} = n + (2^{\log n+1} -1) \leq  n+2 \times 2^{\log n} \leq  n+2n
$$
The amortized cost per insert is therefore $3n /n=3$.
- So, despite it being incredibly expensive to move to a larger table from time to time, the amortized cost per operation is constant.

Now, lets try to solve the same problem with the accounting method.

Every time we insert a new element into the array, we charge 3. 1 to insert, and 2 to expand later. The money to expand can be imagined as giving 1 to an existing number in the array, and 1 to the new guy. This way, when it comes time to expand, everybody has 1. So the expansion is already paid for.
# Insertions and Deletes
Now we factor in deletions. When $\alpha(T)$ is too small, we would like to allocate a smaller table, so we do not use all that memory. Just like last time, we allocate the smaller table before moving everything into that new table.

- Missed something here

Naively, we might just try to halve the size of the table when $\alpha=1 /2$.

For some sequence $\sigma$ of inserts and deletes, starting from a an empty table of size 1. What is the amortized cost using this approach?

Well, in the worst case, for some $n=2^{k}$, lets say we insert $n /2$ elements, filling up a table of size $n /2$. Once this is done, we simply insert, delete, delete, insert, insert. Then oscillate this until we run out of operations. We are constantly expanding and cutting the table in half. This is incredibly slow! The total cost is $\Omega(n^{2})$ and amortized cost $\Omega(n)$.

How will we solve this issue? Instead we will halve the size of the table when we reach $\alpha=1 /4$ instead of $\alpha=1 /2$.

To determine the amortized cost, we will use the accounting method. (No aggregate method because the math is too complex).

After some sequence of inserts or deletes, if the sequence contains $\geq n /2$ inserts, then we might have to expand the table. We know this from before, but think about it this way: the cost of expansion is $n$. We need to pay for $n$ with $n /2$ inserts somehow. 1 for each insert, and 2 to expand.

Now, if there are $\geq n /4$ deletes in the sequence, then we might have to contract the table. Since we are moving $n /4$ elements to a new table, this costs $n /4$. We therefore choose to charge 2 for each delete.