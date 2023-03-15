#Distributed-Systems 

Example: BitTorrent

![[Pasted image 20230315212332.png]]
- When a node is joining: traditional client server
- When a node has joined: decentralised structure
- To download a file, a user needs to access a global directory containing references to torrent files.  
- A torrent file contains the information that is needed to download a specific file, such as a link to a file tracker, a server that keeps an accurate account of active nodes that have (chunks of) the requested file.  
- Once the nodes have been identified from where chunks can be downloaded, the downloading node effectively becomes active.