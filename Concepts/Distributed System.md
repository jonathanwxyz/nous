#Distributed-Systems

### What is it?
- “A distributed system is a collection of autonomous ==computing elements== that appears to its users as a ==single coherent system==”
	- A computing element or ==node== can be either hardware or software
		- Nodes can be big or small and interconnected in any way
	- A single coherent system: users believe they're dealing with a single system
		- The autonomous nodes (each having it's own notion of time) need to collaborate. 

#### Characteristics of a Distributed System
- Distributed systems can vary in:
	- Size (a few to millions of computers)
	- How nodes are interconnected (e.g. wired, wireless, hybrid)
	- How node membership is handled (e.g. open or closed group)
- Nodes act ==independently== from one another but can't ignore one another
- Programmed to achieve common goals
- Communicate by ==message passing==
- Appear as a single coherent system to users, ==[[Distributed Systems Transparency]]== is an important goal
- Computation is ==concurrent==
- There is ==no shared state==
- Failures occur and we may not know or be told about them
- Communication events have non-negligible duration
- Components may exchange data at variable rates
- Different components process data at different rates

### Examples of Distributed Systems
- The web over the internet
	- Documents, email, media, commerce, etc.
- Mobile Telephony
- Electronic Funds Transfers
- Instant Messaging

### Why?
- To ==share== resources
- To bind customers and suppliers (==cooperation==)
- Better ==performance/cost== ratios
- ==Scale== by allocating additional resources to the computation when demand increases
	- Allows for incremental expansion and contraction
- Increase ==reliability== and ==availability== in certain scenarios

### Fallacies about Distributed Systems
[[Fallacies about Distributed Systems]]
