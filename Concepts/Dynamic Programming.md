### Requirements
==Optimal Substructure==. This is similar to [[Divide and Conquer]]. We need  
1. ==Simple/Similar subproblems== - We can break the problem down into identifiable subproblems with the same structure  
2. ==Subproblem optimality== - We can put (optimal) solutions of subproblems together to produce a global (optimal) solution.

==Overlapping Subproblems==. Unrelated subproblems contain subproblems in common.  
This is the key difference to divide-and-conquer.

### Implementations
- ==top-down== with [[Memoization]]
	- Here we start with the big problem we want to solve use divide and conquer to break the problem down, caching the values calculated
- ==bottom-up== with [[Tabulation]]
	- Here we "fill a table" with values leading up to the big problem we're trying to solve