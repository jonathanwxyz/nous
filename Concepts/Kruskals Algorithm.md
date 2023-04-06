#Algorithms-and-Data-Structures 

### How does it work?
- Make a set from each node
- Rank the edges by the weight between vertices
- Loop through these edges
- If the edges don't belong to the same set then union the sets containing the nodes

This algorithm avoids cycles being made as the edge would already have vertices in the same set which would avoid that edge being added to the solution.

### Algorithm Details
An algorithm for creating [[Minimum Spanning Tree (MST)]] using [[Disjoint Set]]s. 
![[Pasted image 20230403121940.png]]
![[Pasted image 20230403122055.png]]
![[Pasted image 20230403122109.png]]
![[Pasted image 20230403122138.png]]
![[Pasted image 20230403122159.png]]

### Complexity
Depends on the implementation of the disjoint-set data structure
O(|E|log|V|) using path-compression and union-by-rank heuristics