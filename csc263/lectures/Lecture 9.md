In the context of hashing, we will be studying a little bit of probability. Today, we will be investigating *bloom filters*.

A bloom filter is what is called a "probabilistic dictionary" where we maintain the "fingerprints" of the elements in set $S$.

This introduces something interesting when we search though the set. Search can have false positives. If it tells us $x\not\in S$, then we can be certain that is true. But if it tells us $x \in S$, it could be wrong.
- Bloom filters are used to store malicious URLs, for example. A finger print of malicious URLs is kept, and we can visit the site if we know it's not in the set. But if it might be, then we issue a warning
- A full list of URLs would be ~500 mb, but a bloom filter is ~10 mb
# What is a Bloom filter?
We begin with an empty hashmap with $m$ bits, $BF[0, \dots, m-1]$. Then we have $t$ hash functions $h_{1}, h_{2}, \dots$
- Recall that in this course all hash functions satisfy SUHA

So how does it work? Lets say we insert $x$, then we hash it both times with $h_{1}$ and $h_{2}$. The two bits who flip from negative to positive after this operation make up the "fingerprint" for $x$. This an be repeated and expanded with more hash functions and elements.

When we search for $x$, we look for the fingerprint of $x$.
- Apply $h_{1}$ and $h_{2}$ to hash $x$
- If we find 0, it must not be in there
- If we find both 1s, then it might be in there. But it could also just be two overlapping fingerprints
# Probability of a false positive
Say we insert $n$ $x_{i}$ into an empty bloom filter $BF[0\dots m-1]$, with $t$ independent hash functions $h_{i}$.

Now, we search for some value $x$ that is not in the set of $x_{i}$ already in the bloom filter.

To begin, we will compute the probability that $BF[i]$ is still 0 after inserting $x_{1}, x_{2}, \dots, x_{n}$. Where $i$ is some arbitrary index.

Note that for each hash function, the probability that $BF[i]$ is still 0 is:
$$
	1-\frac{1}{m}
$$
After the $t$ hash functions:
$$
	\left( 1-\frac{1}{m} \right)^{t}
$$
After $n$ elements:
$$
	\left( 1-\frac{1}{m} \right)^{nt}
$$
In the limit where $m\to \infty$ this can be approximated as:
$$
	\lim_{ m \to \infty } \left( 1-\frac{1}{m} \right) \approx e^{ -1/m } \implies \left( 1-\frac{1}{m} \right)^{nt} \approx e^{ -nt/m }
$$
This is the probability to find 0 in bit $i$ is this. Equivalently, the probability of finding 1 in $i$ is:
$$
	q=1-e^{ -nt/m }
$$
It is tempting to say that the probability of a false positive is therefore just $q^{t}$. That is, we assume all the $q$ are independent, and multiply them all together. However, it turns out that they are not independent.

However, we can still approximate it by assuming they are all independent from each other. The approximate probability of a false positive is:
$$
	\approx (1-e^{ -nt/m })^{t}
$$
So how do we lower the probability of false positives? In practice, most of the time $m$ is picked before the hashmap, and therefore both $m$ and $n$ are constants.

To minimize this function we therefore require...
$$
	\frac{d}{dt} (1-e^{ -nt/m })^{t} =0 \implies t=\frac{m}{n} \ln 2
$$
# Returning to the URLs
We have a set $S$ of $n=10^{7}$ bad URLs. We'll allocate 8 bits to each URL such that:
$$
	m=8n \implies \frac{m}{n}=8
$$
- Recall that $m$ is the size of the bloom filter
- This is about 10 mb

Now we just need to choose the number of hash functions!
$$
	t = \frac{m}{n} \ln 2 = 8 \ln 2 \approx 5.52
$$
And the chance of a false positive is:
$$
	(1-e^{ -nt/m })^{t} \approx 0.62^{8} \approx 0.0218340105585
$$
Or about 2.2%
