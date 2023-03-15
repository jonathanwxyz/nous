#Distributed-Systems 

![[Pasted image 20230315205321.png]]
- Each node maintains an ==ad hoc list of neighbours==
- Overlay resembles a ==random graph==
	- Edges between nodes only exist with a certain probability
- New nodes often contact a well known node for a list of peers
- Nodes ==change its local list almost continually==
- Looking up data cannot follow a predetermined route
- ==Searching for data is necessary==
- Notably in unstructured P-2-P systems, locating relevant data items can become problematic as the network grows, causing a scalability problem.

### Searching Methods
#### Flooding
![[Pasted image 20230315205656.png]]
- Each node asks all of its connections for a piece of data recursively until found or not found
- Each node records if it's already been requested to avoid infinite loops
- Flooding is very expensive
- ==Time To Live== on requests specifies the max number of hops allowed before a request fails

#### Random Walks
![[Pasted image 20230315205853.png]]
- Each Node asks a random node for data recursively
- Can take a while to find data
- The source node might send out many walks simultaneously to speed things up
- TTL is also used, or alternatively a node that receives a request can check with the source node whether continuing the walk is necessary or if the data has already been found.

### Improve Scalability
- To improve scalability, make use of ==special nodes== that maintain an ==index of data items==
- This abandons the symmetric nature (each node is equal)
- ![[Pasted image 20230315212028.png]]
- For example collaborative Content Delivery Network (CDN), where nodes may offer hosting for data allowing web clients to access the data quickly
