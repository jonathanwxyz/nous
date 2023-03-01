### What is it?
- When a process forks (using an OS call) it causes two copies of itself to be active concurrently
- The child process is given a copy of the parent process' address space
	- HOWEVER the ==address spaces are distinct==, if either modify a variable the change is not visible to the other process

### Use cases
- Common for client-server type of distributed computing, a server typically forks a child process for each request it receives

### Downsides
- Certain degree of isolation
	- If parent and child need to ==interact and share== [[Threading]] might be a better approach to multi tasking

### Cost
- Because of the copying, forking can be ==expensive==
- In practice modern OSs have strategies that make the actual cost quite ==affordable==

### Safety
- Reasonably safe because the address space is distinct
- Must adhere to best practices to avoid zombie processes and unintended sharing of references to files