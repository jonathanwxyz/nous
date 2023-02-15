#Distributed-Systems 

### Problem
In [[distributed system]]s (particularly [[Distributed System Synchronisation]]]), clock synchronisation is not completely possible by the fact that messages are ==not sent instantaneously== over real networks, and that there usually is some degree of ==variation in the time== messages take ==to arrive at their destination==.

### Solutions
As long some amount of error is acceptable, there are at least two widely acceptable ways for getting clocks in different parts of a system into near-synchronisation.
- [[Cristian's Algorithm]]
- [[The Berkeley Algorithm]]