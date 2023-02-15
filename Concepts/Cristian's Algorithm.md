#Distributed-Systems 

### What is it?
An algorithm to try to solve [[Clock Synchronisation]] and thus [[Distributed System Synchronisation]].

- Cristian’s algorithm works between a process P, and a time server S connected to a source of ==UTC (Coordinated Universal Time)==.  
- It relies on the accuracy of an estimate based on the ==Round Trip Time (RTT)==, which is the elapsed time between the time when a request is sent from P to S, and the time when a response is received by P from S.

### Algorithm
- P requests the time from S.  
- After receiving the request from P, S prepares a response and appends the time T from its own clock. The response is sent to P.  
- P then sets its time to be T + RTT/2, where RTT\* is Round Trip Time of the request P made to S.

\* Assumes RTT is split equally between both request and response. Reasonable on a LAN connection

### Problems
- The clock tends to drift as the RTT isn't completely accurate
- If send and receive do not take the same amount of time then things will also drift
A better algorithm is [[The Berkeley Algorithm]].