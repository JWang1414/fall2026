# Question 3
---
a.
Assuming the index of the first array is one, its children are mapped to $A[3i-1]$, $A[3i]$, and $A[3i+1]$, for each of its children. Their parents are round($A[i /3]$).

A Heapsize variable may be maintained by starting at 1, and incrementing or decrementing everytime a node is inserted or deleted. Alternative, the size of the heap can be determined each time, but I believe this would take $n$ time.

---
b.
The height of a ternary tree is $\lfloor \log_{3}(2n) \rfloor$.
- I got this from stack exchange