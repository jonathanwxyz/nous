#Distributed-Systems 

- ==Network topology== is the way in which nodes of a distributed system are linked.
- Servers may be added and removed all the time, clients connect and disconnect constantly
- The implications:
	- Do not rely on specific endpoints or routes
	- Abstract from the physical structure of the network (e.g. using DNS names rather than IP addresses for referring to an endpoint)