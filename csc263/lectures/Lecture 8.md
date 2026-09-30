Today we will discuss *hash tables*.

Recall our discussion of dictionaries. Which is a dynamic set $S$ with keys $k\in U$ where $U$ is the universe of possible keys.

If the universe $U$ is small, then we might try to use a direct access table. Like a table with 10 entries from 0-9. Operations in this case are quite simple. Just place them in, or remove them directly!
- $\Theta(1)$ complexity for search, insert, and delete operations

This is fast, but what if $U$ is huge? Well creating a table so large is infeasible. Furthermore, in these cases often times $n\ll \lvert U \rvert$. So you are storing less data than keys!
# Hash Tables
To define a hash table we first define some size $m$ of the table $T[0, \dots, m-1]$. We define the hash function $h$, which maps input to some input in the hash table.

When $h(k_{i})=i$, we say $k_{i}$ hashes $i$.

However the hash function is not one-to-one. It is possible for $h(k_{1})=h(k_{2})=i$. To solve this collision issue, we will instead keep a linked list at each table slot. So when two things are hashed to the same slot, both of them enter a sort of queue.
- The new input is placed at the beginning of the linked list. Because then we don't need to traverse to the end of the linked list

Now, to insert something it costs $\Theta(1)$. Delete, assuming we have a pointer to $x$, the cost of removing $x$ is $\Theta(1)$. But search, we must search through the list at $T[h(k)]$. If everybody is hashed into the same slot, then this might take $\Theta(n)$ time.
## Speeding up search
But, how long does this really take on average? Define some empty table $T$ of size $m$ with $n$ keys. Now, how are the hashes defined? In this course we will use a simple uniform hashing algorithm (SUHA):
$$
	\text{Pr}(h(k)=i) = \frac{1}{m}
$$
That is, $k$ is equally likely to hash into any of the $m$ slots. The expected number of items in some slot $n_{i}$ is $n /m$.
- You can prove this, but it's intuitive enough that I won't
- We call this number $n /m$ the *load factor* $\alpha$

Now, for an unsuccessful search through the hash table, it takes $\alpha$ comparison. But on average, for a successful search, it will take $\alpha /2+1$ comparisons. The search time is $\Theta(1+\alpha)$
- The $1+$ is there because it is possible to search an empty hash table. It would take $\Theta(1)$ time in this case, not $\Theta(0)$.

Now, if $n\to \infty$ while $m$ stays constant, the search time will still get slow over time. In this case, we would like to have $m\propto n$, so then $\alpha \propto 1$.

Specifically if we would like $n /m\leq c$ then the size of the table should be $m\geq n /c$.

To accomplish this we would need to allocate a new, larger table, before spending the time to rehash every current element into it. This would take forever!
## How do we choose a hash function?
- Many are trade secrets for competitive advantage

One time example, however, is `k % m`. So the modulo of $k$. A common heuristic for this hash function is choosing $m$ prime.

Why?

Well lets say we chose $m=2^{l}$ instead. Then the modulo would use just the last $l$ bits of $k$ to compute $h(k)$.
- This ultimately results in quite a predictable hash function. So the hashing will be inefficient

Good hash functions use as many bits as possible of the hashed value. This results in more evenly spread keys. And prime numbers are better at guaranteeing this.
