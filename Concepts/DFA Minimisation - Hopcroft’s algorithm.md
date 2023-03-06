![[Pasted image 20230303160703.png]]

### The Problem
Can we minimise the number of states / remove redundant states?

### Answer
- Yes, if we can find groups of states where, for each input symbol, every state of such a group will have transitions to the same group.
- One solution is to start with two groups: final vs non-final states and check if this property holds: if it doesn’t split and keep checking

### Example for (a | b)\*abb
![[Pasted image 20230303161056.png]]
In each iteration, we consider any non-single-member groups and we consider the partitioning criterion for all pairs of states in the group.
We look for whether the respective transitions in each group stay within the group of not. When all of the groups have all of their transitions staying within its group we have a minimised DFA.
![[Pasted image 20230303161138.png]]

