Today we will be considering decision trees for sorting algorithms that take a list of numbers $A=[a_{1},\dots,a_{n}]$ as input and sort it with exclusively comparisons.

Assumptions:
- All input numbers are distinct
- Ignore control flow like data movement. So we model just the comparisons

- Example of a decision tree for insertion sort. This is just the one that was used in lecture already.

The next example will be one for merge sort.
- To model this tree we will use the initial state $[a_{1}], [a_{2}],[a_{3}],[a_{4}]$ where each element has already been split into the single parts.

The first operation is $[a_{1}],[a_{2}]$, which can be merged into $[a_{1},a_{2}]$ or $[a_{2},a_{1}]$, depending on which one is greater.

![[IMG_20261127_154911.jpg]]
![[IMG_20261127_154925.jpg]]
An image of the partial decision tree drawn for merge sort during the tutorial