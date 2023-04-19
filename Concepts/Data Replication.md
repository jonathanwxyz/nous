#Distributed-Systems 

In [[Distributed System]]s, data replication is the idea of having data on multiple systems. This is used for:
- Enhancing system ==reliability==
	- If one ==replica crashes==, the system can continue working by switching to another replica
	- Also can ==protect against corrupted data==
- Improving ==performance==
	- This can come in terms of placing data closer to users geographically, decreasing ==time to access==
		- Although there may be better performance for clients, there might still be more overall network bandwidth used to keep all replicas up to data
	- Helps the system scale in terms of size, more compute power is needed to handle all of the processes wanting to access data
- It can also improve ==scalability==
A major challenge is ==keeping data replicas consistent==

### Price of Replication
> The problem with replication is that having ==multiple copies== may lead to  
==consistency problems==.

Keeping consistency has a cost, must ensure that all copies have the same data.
- Keeping multiple copies up to date may require more network bandwidth.  
- Keeping multiple copies consistent may itself be subject to serious scalability problems

#### Example: Improving web page access times
To improve performance, web browsers often ==cache== web pages
- pros: excellent access time from a user viewpoint
- cons: requires refetching for  latest version of a page

the cached data might be out of data, there are two solutions discussed below:
1. Always fetch pages from the server
	1. poor access time
2. Allow web server to invalidate or update each cached copy
	1. degrade the overall performance

### Tight Consistency through Synchronous Replication
- To guarantee tight consistency, a data ==update== should be performed to ==all data copies== at the same time  
- In other words, an update must performed at all copies as a ==single atomic operation.==  
- Implementation of such atomic operation, involving potentially a large number replicas, is inherently difficult:  
	- The replicas may be widely dispersed across a large-scale network.  
	- Operations on the replicas may be required to complete quickly.

### Relaxing Tight Consistency
- ==Global synchronization takes a lot of communication time==, especially when replicas are spread across a wide-area network.  
	- Solution: relax the consistency constraints.  
- The ==(instantaneous) global synchronizations are avoided== if consistency constraints are relaxed, performance may be improved.  
	- Cons: replicas may not always be the same everywhere
- Global synchronization takes a lot of communication time, especially when replicas are spread across a wide-area network.  
	- Solution: relax the consistency constraints.  
	- The (instantaneous) global synchronizations are avoided if consistency constraints are relaxed, performance may be improved.  
- Cons: replicas may not always be the same everywhere

### Consistency Models
#### Assumptions
- Assuming that there is a data store to which multiple processes running on different machines have access, a consistency model is a “contract” between the processes and this data store.  
	- The store “promises” to work correctly provided that the defined rules are obeyed by the processes.  
- Local write operations (performed on copy of the data) are propagated to the other copies.  
- A data operation is classified as a write operation when it changes the data, otherwise, is a read operation.  
- Any consistency model restricts the values that a read operation on  a data item can return.
![[Pasted image 20230407125935.png]]

#### Sequential Consistency Model
- A data store is sequentially consistent when it satisfies the condition:  
> "The result of any execution is the same as if the (read and write) operations by all processes on the data store were executed in some sequential order and the operations of each individual process appear in this sequence in the order specified by its program."  
- There is no involvement of time; no reference to the “most recent” write operation.
![[Pasted image 20230407130314.png]]
- The above example is sequentially consistent because P3 and P4 agree that Wb comes before Wa, despite the diagram
![[Pasted image 20230407130410.png]]
- This example violates sequential consistency

#### Causal Consistency Model
- A data store is causally consistent if it satisfies the condition:  
> "Writes that are potentially causally related must be seen by all processes in the same order. Concurrent writes may be seen in a different order on different machines."  
- This model distinguishes between events that are possibly causally related and those that are not.  
- For example, if event b is caused or influenced by an earlier event a, causality requires that “everyone else” first sees a, then see b.  
- Operations that are not causally related are said to be ==concurrent==
![[Pasted image 20230407130812.png]]
- The above example is NOT causally consistent
	- Because of the Ra in P2 p1 and p2 now have a causal relation where we'd expect there to be Ra then Rb which is not what we see in P3
![[Pasted image 20230407130906.png]]
- This is causally consistent

### Replica Management
- It is about where, when, and by whom replicas should be placed, and subsequently which mechanisms to use for keeping the replicas consistent.  
- In its general form, it is a classical optimisation problem, but in practice it is often a management/commercial issue!
![[Pasted image 20230407131005.png]]

#### A Greedy Heuristic to Find Locations
1. Find the total cost of accessing each site from all the other sites. Choose the site with the minimum total cost.  
2. Repeat (1) above, taking also into account sites hosting replicas (i.e., recalculate costs).

![[Pasted image 20230407131150.png]]
Node M has the minimum cost!  
Once we chose M, the next iteration  
may take into account the fact that sites  
attempt to access the nearest replica

step 2: after choosing M for replica hosting
![[Pasted image 20230407131224.png]]
- Can (naively) just remove node M and repeat to find another node.  
- Better, but more work, replace each value in the table by min(value, value-to-M)  
- Note that this destroys any symmetry it had initially:

