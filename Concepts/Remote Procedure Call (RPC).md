#Distributed-Systems 

### What is it?
The idea behind RPC is to make a remote procedure call look as much as possible like a local one, ==hiding== most of the intricacies of ==message passing==. RPC is an abstraction over `send` and `receive` which send messages and block to await a message from a remote server respectively.

### Step by step
1. The client procedure calls the client stub in the normal way.
2. The client stub builds a message and calls the local operating system.
3. The client’s OS sends the message to the remote OS.
4. The remote OS gives the message to the server stub.
5. The server stub unpacks the parameter(s) and calls the server.
6. The server does the work and returns the result to the stub.
7. The server stub packs the result in a message and calls its local OS.
8. The server’s OS sends the message to the client’s OS.
9. The client’s OS gives the message to the client stub.
10. The stub unpacks the result and returns it to the client.
![[Pasted image 20230403102743.png|500]]

### Parameter Passing
- The function of the client stub is to take its parameters, pack them into a message, and send them to the server stub.
- Packing parameters into a message is called ==Parameter Marshalling==
	- This is not straightforward
	- The server just sees a series of bytes
	- The data must be transformed into a ==machine and network independent format==
		- Accomplished by using machine-dependent routines that transform the data to and from independent formats.
	- Also making sure that ==both communicating parties expect the same message data type==
		 - Typically solved at the level of programming languages
- Marshalling is all about this transformation to neutral formats and forms, an essential part of remote procedure calls.

### Passing References to Objects
- Pointers or references are passed by copying the entire data structure to which the parameter is referring.
- Effectively replacing the copy-by-reference mechanism with ==copy-by-value/restore==

### Asynchronous RPCs
In some situations, there is no result to return to the client. In these cases it is wasteful for the client to block for the entire duration of the computation on the server.

Instead Async RPCs can be used where the server sends an ==acknowledgement== to the client as soon as the message is received. The client will continue without further blocking as soon as it has received the server's acknowledgement.
![[Pasted image 20230403105746.png|500]]
