#Algorithms-and-Data-Structures 

This is an algorithm for finding [[Shortest Paths]] in ==Weighted Graphs==
For instance, look at this problem of navigating from Berlin to Munich:
![[Pasted image 20230215170742.png]]

### Definitions
- The [[Graph]] is represented as a weight matrix
	- ![[Pasted image 20230215170849.png]]
	- E = {(u,v)|w(u,v) != $\infty$}
	- w(u,v) = d - Edge between u and v has weight d
	- w(u,v) = $\infty$ - No edge between u and v
- Path p is a list of nodes
	- Path between u and v: upv
	- Weight of path: ![[Pasted image 20230215171342.png]]
	- |p| = $\infty$ means path p not feasible!
- $\delta(u, v)$ - distance between u and v
	- $\delta(u,v)$ := min|upv| for all paths p
	- $\delta(u,v)$ := $\infty$ - No path from u to v!

The shortest path is not always unique, could be multiple.

Notation: $\delta(u)$ := $\delta(s, u)$

### Algorithm
![[Pasted image 20230215172038.png]]
- Over estimate shortest path to all vertices
	- D(u) >= $\delta(u)$
	- D(s) = 0, D(u) = inf, u != s
- Iterate over all edges  
	- For an edge a→b ,
		- If we can get to b quicker than we could previously, then update our estimation on b.  
- Repeat for upto |V|-1 rounds

### Complexity
- In worst case we do |V| (number of vertices) rounds
- Each round inspects |E| (number of edges) edges
- Time for relaxing edge: O(1)
- Complexity is O(|V||E|)

### Correctness
Uses [[Loop Invariant]] technique.

- Claim in round I:  
	- Estimated shortest paths upto length I are precise  
	-  ![[Pasted image 20230215173447.png]]
- Initial Claim:At the end of round 0, D is precise up to length 0  
- Assume: that at the end of round i,D is precise up to length i  
- Show: that at the end of round i+1, D is precise up to length i+1  
	- Prefix of a shortest path is also a shortest path  
	- Assume the path “s→P→ u → v” is a shortest path of length i+1  
	- Therefore “s→ P → u” is a shortest path of length i, and we know that D(u) is precise.  
	- Round i+1 relaxes the edge (u,v)  
	- Now D(v) is precise after round i+1

### Negative Weight Cycles
No shortest paths to nodes reachable from cycle

Can be detected:
	- Iterates until D does not change
	- If D still changed in |V|th round: report negative cycle
![[Pasted image 20230215174333.png]]

