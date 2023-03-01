## A* in AI
A form of [[Breadth-First Search]] where we try to find the optimal solution.

![[Pasted image 20221011134928.png]]
When we order the Queue, we want the node with the smallest K at the front of the queue

## A* in Shortest Path
Very similar to [[Dikjstra's Algorithm]] however we use a heuristic in order to avoid searching many of the nodes to speed up the algorithm.
The actual complexity is equal to [[Dikjstra's Algorithm#Complexity|dikjstra's complexity]].
In this algorithm, once we've found a path to the goal node we stop searching, the heuristic hopefully will have given us an optimal or near optimal solution. So we order the PQ by the heuristic and pop off the best values that have the lowest heuristic value.

### Psuedocode
```python
dijkstra(s):  
	F = EmptySet  
	D = initEstimate(s)  
	while(notEmpty(D)):  
		u = D.pop()  
		if u == goal:  # new compared to dikjstra
			return D(u)  
		F.add(u)  
		for each u,v, where v not in FUD:  
			D.add(v, heuristic(v))  
		relax(u)  

relax(u):  
	for each u,v:  
		if D(u) + w(u,v) < D(v):  
			D(v) = D(u) + w(u,v)  
			P(v) = u

heuristic(v):
	return D(u) + Distance to Munich/100
```

### Heuristic Admissibility and Monotonicity
- To use an heuristic it must be:  
	- Admissible  
		- ie: it must not overestimate the true cost of reaching the destination  
- Monotone 
	- ie: Fits the triangle inequality
	 - ![[Pasted image 20230227161636.png]]

  ### Correctness
  See [[Correctness of Dikjstra and A*]]