#Distributed-Systems 

An architectural style for [[Distributed System]]s which ==encapsulates services== into independent units. This allows developers to ignore the internal workings of each service that they're working with if they're ==composing== them into a larger application.

![[Pasted image 20230516115754.png]]
The services don't even need to be made by the same organisation.

### What is a service?
A service is considered as a discrete ==unit of functionality== that can be ==accessed remotely==, via a network, and updated independently. However, a service can possibly make use of other services.

### Service Composition
- ==Not a trivial problem==
- Must ensure that services operate in harmony
- The services must offer an interface