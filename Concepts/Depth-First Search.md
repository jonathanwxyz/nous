call `dfs([StartNode])`
![[Pasted image 20221011132731.png]]
In this case a Queue is basically a Stack; last in, first out (LIFO).
The queue is initialised to the start node
Here we search the tree branch by branch.

![[Pasted image 20221011133500.png]]
Same as previous example however we call each dfs on each daughter separately rather than putting them in the same queue.

### Depth-First Search + Pruning
An example of this is [[Branch-And-Bound]]

### Related
- [[Breadth-First Search]]