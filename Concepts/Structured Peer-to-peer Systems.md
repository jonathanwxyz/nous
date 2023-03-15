#Distributed-Systems 

![[Pasted image 20230315204746.png]]
- Nodes are organised in an overlay to a ==specific, deterministic topology==
	- A ring, a binary tree, a grid, etc.
- ==Efficiently look up data==
	- You know where to look
	- Through hashing you can identify where to look for specific data you're looking for
		- i.e., each data item is uniquely associated with a key, typically obtained by a hash function on the data item’s value. This key is used as an index, since it identifies a node in the system.
		- `key(data item) = hash(data item’s value)`
- any node can be asked to look up a given key, i.e., to ==efficiently route a request for data to the node responsible for storing the data associated with the given key.==