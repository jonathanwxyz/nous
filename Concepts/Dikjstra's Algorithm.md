#Algorithms-and-Data-Structures 

### What is it?
An algorithm for finding the fastest path between two nodes in a weighted [[Graph]].
We consider all nodes, however it is faster than [[Bellman Ford Algorithm]] as we only consider reachable nodes.

### Pseudocode
```python
dijkstra(s):  
	F = EmptySet  #Finished nodes
	D = initEstimate(s)  #Discovered Nodes
	while(notEmpty(D)):  
		u = D.pop()  
		F.add(u)  
		for each u,v, where v not in FUD:  
			D.add(v)  
		relax(u)  
relax(u):  
	for each u,v:  
	if D(u) + w(u,v) < D(v):  
	D(v) = D(u) + w(u,v)  
	P(v) = u
```

### Implementation Details
- Using a [[Priority Queue]]:  
	- Relaxation means a node’s value may decrease  
	- We need a decrease key operation  
	- Use a [[Binary Heap|MinHeap]] and restore heap-property after pop,insertion,relaxation operations.
- By adding nodes as they are discovered rather then adding all nodes to D upfront
	- We wont explore any unreachable nodes  
	- No need for infinity in the PQ
- Use predecessors to backtrack and find shortest path
	- ![[Pasted image 20230227123641.png]]
	- For example the image above shows the fastest path from Berlin to various places
	- Berlin to Munich takes 6 units, to figure out the path we see that we must go from Chemnitz to Munich, fastest path to Chemnitz is from Magedeburg, fastest path to there is from Berlin
 

### Complexity
- Operations:  
	- Every edge is relaxed at most once  
	- Every node is added and removed from PQ at most once  
- Cost of relaxing, addition, extraction within the min heap PQ: O(log |V|)  
- O((|E| + |V|) log(|V|))

  ### Correctness
  See [[Correctness of Dikjstra and A*#Dikjstra]]