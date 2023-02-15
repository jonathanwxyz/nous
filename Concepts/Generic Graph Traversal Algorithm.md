#Algorithms-and-Data-Structures 

### Algorithm
- Explore edges to new nodes, until all nodes discovered  
- Create sets as we go:  
	- D: discovered, but outgoing edges yet to be explored  
	- F: finished, outgoing edges have been explored
```haskell
procedure EXPLORE (s)  
	D ← { s }, F ← ∅  
	while D ≠ ∅ do  
		u ← Some u ∈ D  
		D ← D \ { u }, F ← F ∪ { u }  
		D ← D ∪ { v | (u , v) ∈ E ∧ v ∉ F }  
return F
```
- EXPLORE (s) returns exactly the nodes reachable from s
![[Pasted image 20230208110635.png]]

### Correctness
EXPLORE (s) returns exactly the nodes reachable from s  
- Any node in D ∪ F is reachable:  
	- Initially, only s ∈ D ∪ F  
	- only successors of nodes in D ∪ F added  
- If a node is reachable, it will be included in F:  
	- During the loop, successors of finished nodes are finished or discovered  
	- Finally, D = ∅, thus successors of finished nodes are finished  
⇒ every reachable node is finished (follow path from s)

### Order
In what order should we traverse nodes from D?
- LIFO (Stack): [[Graph Depth First Search]]
- FIFO (Queue): [[Graph Breadth First Search]]