# Exercise 1 Report

### The Protocol
The protocol is very simple, there are 3 keys stored on the server:
1. connected: The number of clients connected
	- This stores the values of '1' or '2'
1. lock: A lock to indicate which client gets to send a message
	- This stores the values of '1' or '2'
1. message: The last message sent
	- This stores the value of the last message sent as a string

### Synchronisation Between Clients
The protocol achieves synchronisation between 2 clients through assigning the roles of 'client 1' and 'client 2' based on which of the clients were first to connect to the server.

At the beginning of the execution of the program with no connected clients, the server key 'connected' has a null value (or the cell doesn't exist). The client changes this to make the value 1, and sets itself as client 1. When the other client begins the program, they'll find that the 'connected' is 1, indicating that they will be client 2. client 2 sets 'connected' to 2, indicating to client 1 that both clients are now connected.

Initially, the 'lock' is set to 1, meaning client 1 gets to message first. Client 2 blocks until the lock changes to 2, at which point client 2 prints the 'message' field. Meanwhile client 1 allows the user to set a message which will change the 'message' field, at which point the client switches the lock to 2. This keeps alternating until the clients are done talking

### How to Test
In order to test 