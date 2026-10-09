Example exam question. Optional assignment problem.

> Words from a dictionary of size $l$ come in one at a time. At any point between two words, you may be asked to output the most frequent word starting with each letter from a-z.

We would like $\Theta(1)$ expected time for each input word, and $\Theta(1)$ worst case for each query.

We will use a hash table $T$ of size $m$. Each entry will be a word, paired with its count.

Assume SUHA hash function, that can be done in constant time, so that the entries are evenly distributed across the hash table, thus achieving the $\Theta(1)$ look-up times. Furthermore, note that $m\in \Omega(l)$ in order to achieve our needed running time.

Now, we will use a direct-access array $A$, accessed with each character from a-z. $A[c]$, for example, gives us the most frequent word starting with $c$.

> Explain in plain english

When we get a word, we hash to the hash table $T$. If the word exists in the chain, increment its counter. Otherwise, store the word with a count of 1. Check the corresponding entry in $A$, and update it if the new word appears more frequently.

Basically:
1. Insert/increment new word in hash table
2. Compare new word count and $A$ count
3. Adjust $A$ to the new max

- Note that if the new word is smaller in dictionary order, it has priority. And so $A$ updates even if the two words begin with the same letter.

Insert(w)
```
h = hash(w)

if (w is in chain T[h]):
	Increment w's counter
else
	Store w with a count of 1 in T[h]

if (T[w] > T[A[w[0]]] or (T[w] == T[A[w[0]]] and w < A[w[0]])):
	A[w[0]] = w
```

Where we have used $T[w]$ and $T[A[w[0]]]$ as a shorthand for settings $w$'s count in the hash table, or zero if it doesn't exist.

Query()
```
for word in A:
	print(word)
```

The runtime of Query() is constant because $A$ has a set length 26. Printing is constant time. The runtime is therefore:
$$
	1 \times 26  \in \Theta(1)
$$
From our assumptions, SUHA will take constant time, and look-ups are expected to take constant time (because $m=\Omega(l)$). During the course of insertion, we complete 3 look-ups, so the runtime is,
$$
	1+1+1 \in\Theta(1)
$$
