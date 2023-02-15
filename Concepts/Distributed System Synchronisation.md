#Distributed-Systems 

See first: [[Synchronisation]]
### Synchronisation Challenges in DS
- [[DS Fallacy - The network is reliable|As the network is not reliable]], coordination of actions that depend on communication over a network is quite challenging.
- The only thing that is certain about two nodes with independent clocks is that a message will not arrive at its destination before it is sent
- Potential solutions:
	- Timestamps, trouble is that the clocks might not be in sync
	- Send synchronisation message, trouble is that there is no way of knowing exactly how long a message will take to arrive

### Example of obtaining the order of events
![[Pasted image 20230214155747.png]]
Assumptions:  
1. P and Q are two distinct processes running on different nodes, each executing a sequence of instructions, p1 to p5 and q1 to q3, respectively.  
2. The dotted lines represent the transmission of a message from one process to another.  
3. P and Q do not have any shared notion of time.

What can we say about the ordering of events?
- Nothing about p1 and q1
- q2 is after p2 as q2 relies on p2
- Nothing about p3 and q2, it's possible that p3 finished right after p2 and finished before q2, or p3 finished after q2
- In spite of the visual order, p4 happens after q3
- We know p5 happens after q3 because it relies on p4 which relies on q3

So the sending and receiving of messages between components gives us an implicit partial ordering of events whether we intend it or not, because a message never arrives before being sent.

### Happens Before (->) Notation
- If $a$ and $b$ are in the same process and $a$ occurs before $b$ then $a$ -> $b$ is true (read as $a$ happens before $b$)
- If $a$ is the event of a message being sent by one process, and $b$ is the event of a message being received by another process then $a$ -> $b$ is true
- -> is a transitive relation relation so if $a$->$b$ and $b$->$c$ then $a$->$c$
- If two events x and y happen in different processes that do not exchange messages (directly or indirectly) then x -> y is not true and neither is y -> x. These events are said to be [[Concurrency|Concurrent]]

### Logical Clocks
See [[Logical Clocks]]
### Stopping Events from Happening Simultaneously When Sharing Resources
#### Example: Selling a game ticket to a client
- The involved components include a database of available tickets
- at least two bank accounts (one for the ticket vendor, one or the person buying the ticket
- and possibly other systems for validating addresses
- and arranging for the ticket to be delivered electronically.

These systems need to be ==choreographed to act as one== when selling a ticket to avoid situations such as:
1. Selling a ticket which happens to be the last ticket, only for the ticket to be sold midway through the process
2. When paying for the ticket, a crash occurs which means the seller doesn't receive the money but the client lost their money

#### Possible Solutions
- [[Centralised Lock Server]]
- [[Two Phase Commit Algorithm]]

### Clock Synchronisation
See [[Clock Synchronisation]]