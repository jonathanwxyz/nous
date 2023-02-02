1. Explore a tree of partial solutions  
2. Prune branches and backtrack  

In backtracking we prune a branch if it can not be extended to a solution at all  

In branch-and-bound we prune a branch if it can not produce a better solution  
than one that exists on another branch

![[Pasted image 20221011134645.png]]
This is a [[Depth-First Search]] but takes costs into account and minimises it.