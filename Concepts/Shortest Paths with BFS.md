- Shortest path from s to some node?  
	- Shortest = minimal number of edges  
- [[Breadth-First Search|BFS]] visits nodes in order of their distance from s!  
- Obtain path via ==predecessor== map:  
	- For each node, store node from which it was discovered  
	- Follow these nodes backwards, until s is reached  
	- Convention: predecessor of s is s itself.

### Algorithm
```C
procedure SHORTESTPATHS (s)  
	D ← [s], F ← ∅, π(s) ← s  
	while D ≠ [] do  
		u ← DEQUEUE(D)  
		F ← F ∪ {u}  
		for all v with(u, v) ∈ E ∧ v ∉ F do  
			ENQUEUE(D, v), π(v) ← u  
return π
```
- pi is predecessor
- `u ← DEQUEUE(D)`: return u, the element formerly at the front of D, and remove u from D
- `ENQUEUE(D, v)`: add v to the end of D

```c
procedure GETPATH(π, u)  
	p ← [u]  
	while π(u) ≠ u do  
		u ← π(u), p ← up  
return p
```
- For each node v, predecessor map π(v) stores the node from which v was discovered

To use this algorithm we must call `SHORTESTPATHS` with our start node. Then we can call `GETPATH` with the predecessors and the node we want to get the shortest path to. This will return the shortest path.
![[Pasted image 20230215163745.png]]
![[Pasted image 20230215163758.png]]
