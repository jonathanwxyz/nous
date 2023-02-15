#Algorithms-and-Data-Structures 

### Algorithm
Same as [[Generic Graph Traversal Algorithm]] However in the List D of nodes left to explore we treat it as a stack (LiFo) and pop nodes off the stack accordingly.

### Recursive Implementation
There is a nice recursive implementation of this algorithm
```haskell
procedure DFS R EC(F, u)  
	if u ∉ F then  
	F ← F ∪ { u }  
	for all v with (u, v) ∈ E do  
	F ← DFS R EC(F, v)  
	return F  
procedure DFS (s)  
return DFS R EC(∅, s)
```

### Related
[[Depth-First Search]]