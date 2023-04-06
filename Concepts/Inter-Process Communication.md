#Distributed-Systems 

### What is it?
- Inter-Process Communication encompasses the ways that ==processes on different machines== can ==exchange information==
- Traditionally based on ==low-level message passing== offered by the ==underlying network==
	- This is harder to realise compared to communication based on shared memory, as is in non-distributed systems
- Given unreliability of the internet, large scale comms are difficult
- Two widely-used models for communication are:
	- [[Remote Procedure Call (RPC)]]
	- [[Message-Oriented Middleware (MOM)]]