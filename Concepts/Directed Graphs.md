#Algorithms-and-Data-Structures

### What is it?
A directed graph is a set of nodes (Vertices) $V$ and edges $E$ , where 𝐸 ⊆ 𝑉 × 𝑉.
![[Pasted image 20230131142348.png]]
V = { 1, 2, ..., 9 }
E = { (1, 2), (1, 3), (2, 4), (2, 5), (3, 6), (3, 7), (4, 8), (4, 9), (6, 5), (9, 2) }
	- First element of the tuple is 'from', second is 'to'
*Undirected Graphs*: edge pairs are not ordered (no arrows on visual representation)

==Path==: Sequence of nodes $u_1 ... u_n$, with $\forall i \in {1 ... n - 1}$ and $(u_i, u_{i+1}) \in E$

### Cycles
A ==Cycle== is a path with same start and end node

### Simple Graphs
- No parallel edges (two edges with same origin and destination)
- No self-loops (origin same as destination)

### Subgraph
Some of the edges, some of the vertices of the parent graph
### Spanning Subgraph
A subgraph that contains all of the nodes but not all of the vertices

### Operations
- EMPTY returns empty graph. E ← ∅  
- ADDEDGE (u, v) adds an edge. E ← E ∪ { (u, v) }  
- REMOVE EDGE (u, v) removes an edge. E ← E \ { (u, v) }  
- IS EDGE (u, v) checks for edge. (u, v) ∈ E  
- SUCCS (u) returns successors of node. {v | (u, v ) ∈ E }

### Implementations
#### Adjacency List
Store list/set of successors for each node
![[Pasted image 20230208104555.png]]
- Map each node to list of successors  
	- E = { (u, v) | v ∈ succs(u) }  
	- directly implements succs(u)  
	- for integer nodes: use array of (dynamic) arrays
- Memory O(|V| + |E|)
![[Pasted image 20230208104833.png]]
#### Adjacency Matrix
- m(u, v) = TRUE iff edge from u to v
![[Pasted image 20230208105006.png]]
- Store |V| × |V| map to Booleans  
	- E = { (u, v) | m(u, v) = TRUE }  
	- for integer nodes: use 2-dimensional array  
- Memory O(|V|^2)  
	- Bad for sparse graphs (|E| ≪ |V| 2)
![[Pasted image 20230208105113.png]]
