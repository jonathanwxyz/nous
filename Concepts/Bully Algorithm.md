#Distributed-Systems 

### What is it?
- The Bully Algorithm is a mechanism for choosing a coordinator from a set of candidate nodes.
	- The algorithm gets its name from the fact that higher numbered nodes ‘bully’ lower numbered nodes into submission

### How does it work?
- P sends an ELECTION message to all nodes with higher numbers.  
- If no one responds, P wins the election and becomes the co-ordinator. It informs all the other nodes that it is now the coordinator.  
- If one of the higher-numbered nodes Q answers, P concedes that it is not the winner, and Q begins the election process again until one node eventually wins.

### Notes
1. the algorithm relies on the use of timeouts to decide when to give up’ waiting for responses from nodes that have potentially died (so the usual problem of ‘how long is it reasonable to wait’ applies here).
2. the algorithm assumes that the participating nodes are ordered.