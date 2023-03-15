#Distributed-Systems 

![[Pasted image 20230315202416.png]]
- In this architectural style, processes running on the various components are both ==referentially decoupled== and ==temporally coupled==. In other words, one process does not explicitly know any other process, but for coordination to take place processes need to be running at the same time.
- In such scenarios, the only thing a process can do is publish a notification describing the occurrence of an event).
- Processes may subscribe to a specific type of notification