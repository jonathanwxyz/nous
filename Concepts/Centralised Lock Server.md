#Distributed-Systems 

### What is it?
A ==Centralised Lock Server and Mutual Exclusion Locks (Mutex)== is an architecture for [[Distributed System Synchronisation]] which allows for atomic operations, although it isn't perfect.

### Client
1. Sends a request to the lock server for a mutex on a given resource.
2. When a reply comes back, it starts executing its critical process over the resource.
3. When its finished, it sends a message to release the mutex

### The Lock Server
1. If the resource is available, it marks it as being used by the client and sends a reply to say that the lock has been granted. Otherwise, it puts the request in a queue.
2. When the mutex is released by the client, if another client wants the resource (i.e., is in the queue waiting), pass the mutex to them, otherwise mark it as being available.

### Notes
1. This solution presents a basic limitation: a ==single point of failure== (i.e. the central lock server).
2. Although the solution is able to protect sequences of events that need to be treated as ‘atomic’ (indivisible) operations, ==it cannot make sure that, if any part of the sequence of event fails, the state of the system remains unchanged==.
