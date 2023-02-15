### What's is it?
- Set of tasks, e.g.  
	- A build sequence when developing software  
	- Prerequisites between courses of a degree  
	- Scheduling task constraints in a project  
- Dependencies, i.e. tasks that needs to be completed before a task can be started
- Model as [[Directed Graphs|directed graph]]:  
	- Edge (u, v): v depends on u.

### Implementation
- Arrange nodes sequentially, such that all edges point forwards  
	- Intuition: All prerequisites come earlier in sequence  
- Topological sorting possible iff graph has no cycles  
	- Directed Acyclic Graph (DAG)  
- Now: DFS based algorithm for topological sorting and cycle detection

#### Algorithm
- When first encountering a node, mark it as O(pen)  
- Only when finished exploring its children, mark it as D(one)  
- Whenever we encounter an open node again, it’s a cycle  
- When node is done, all its successors are already done  
⇒ Nodes done in reverse topological order  
- To get topological sort: prepend nodes to list when marked as done

```haskell
procedure DFS R EC(F, u)  
	if F(u) = N then  
		F(u) ← O // Start processing node  
		for all v with (u, v) ∈ E do  
			F ← DFS R EC(F, v)  
		F(u) ← D // Done processing node  
	else if F(u) = O then  
		Error: found cycle  
return F  
procedure DFS (s)  
	for all nodes u  
		F(u) ← N  
return DFS R EC(F, s)
```

Example with cycle:
![[Pasted image 20230208113925.png]]