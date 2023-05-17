#Distributed-Systems 

A fault tolerant system ==remains operational== in an acceptable way, ==despite the occurrence of failure==.

### Dependability
- Availability
	- The probability that the system operates correctly at any given moment
- Reliability
	- The length of time that the system can run continuously without failure
- Safety
	- If an when a failure occurs, the consequences are not catastrophic
- Maintainability
	- How easily a failed system can be repaired

### Failure
A system fails when it ==fails to meet its promises==
e.g. one or more services cannot be (completely) provided

### Types of Failures
![[Pasted image 20230516122029.png]]
The most serious type is the arbitrary failure
- clients should be prepared for the worst
	- Example: A server starts producing outputs that it should never produce, but which cannot be detected as being incorrect
- Also known as Byzantine failures

### Types of Redundancy used in Fault Tolerance
- Physical redundancy: a well-known engineering technique. Examples can be found in may places, e.g., aircrafts such as B747s or A380s have four engines but, subject to certain conditions, can fly on three.  
- Time redundancy: an action is performed, if need be, again and again. It is especially helpful when faults are transient and intermittent.  
- Information redundancy: e.g., send extra bits when transmitting information to allow recovery
This has the same problems as [[Data Replication]].
We still need to make sure that any failure won’t leave our system in an inconsistent (corrupted) state!
- For example an action consisting of multiple operations, and a crash occurs midway through the action

### ACID
- Atomicity
	- A sequence of operations MUST execute as an ==atomic== operation
- Consistency
	- An application should not violate a database's integrity constraints
- Isolation
	- 
- Durability
	- Updates are persistent once the application successfully completes

#### Transactions
'Transactions' implement the ACID properties for database applications.
to create a transaction you have a `begin_tx`, you then specify the instructions to execute and then have a `commit_tx`. This signals that everything within the transaction is to be executed atomically.
It is fast, recovers from all sorts of failures, highly available and manages concurrency

##### Implementation
- Managing multiple “simultaneous” users  
	- Concurrency control algorithms  
		- Ensure the execution is equivalent to a “serial” execution (key assumption: transactions have a short duration in the order of milliseconds: you don’t want to “block” other transactions for too long).  
- Durability  
	- Recovery algorithms  
		- Replay the actions of committed transactions and undo the effects left behind by aborted transactions


### Concurrency Control
Can be controlled with Locks
- Two-phase locking  
	- “Acquire locks” phase  
	- Get a read lock before reading  
	- Get a write lock before writing  
	- Read locks conflict with write locks  
	- Write locks conflict with read and write locks  
- “Release locks” phase when the transaction terminates (commit or abort)

### Replication of Processes
Another way of achieving fault tolerance is to replicate processes.
There is a ==price to pay==, loss of performance
Most existing solutions require exchange of ==numerous messages between processes==
