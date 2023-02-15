#Distributed-Systems 

### What is it?
The ==Two Phase Commit Algorithm== ensures that a sequence of events either runs to ==successful completion==, or, if the sequence fails, that the overall system is ==returned to its original state== as though nothing had happened. In other words, it allows intermediate steps that have occurred to be ==undone== (i.e., rolledback) to return things back to a safe, sensible state, if a fault is detected. Useful for [[Distributed System Synchronisation]].

### How does it Work?
- A coordinator node\* requests a transaction, and sends a request to all participants nodes  
	- e.g., to node C1, it sends ‘request to remove X pounds from account’, and to C2 sends ‘request to add X pounds to account’.  
- All participants respond as to whether they are willing and able to execute the request, and send VOTE_COMMIT or VOTE_ABORT.  
	- They log their current state, and then perform the transaction.  
	- All participants log their vote  
- The coordinator looks at the votes. If everyone has voted to commit, then the co-ordinator sends a GLOBAL_COMMIT to everyone; otherwise it sends a GLOBAL_ABORT.
- On receiving the decision from the coordinator, all participants record the decision locally. If it was an ABORT, participants ROLL BACK to their previous safe state.

\* Potential point of failure or bottleneck! [[Electing a Coordinator Node|Which node should be the coordinator?]]