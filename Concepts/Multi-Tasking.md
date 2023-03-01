#Distributed-Systems 

### What is OS Multi-Tasking?
- Allows more than one process to be underway by ==controlling== how each one makes use of the ==resources== allocated to it
- Uses a scheduling policy
	- Grants each active process a time slice during which it can access the resources allocated to it
- Processes are not really executing concurrently
	- it only feels like it
	- This can be thought of as ==weak concurrency==