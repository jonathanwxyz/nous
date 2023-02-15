### What is Synchronisation?
Two main forms:
- ==Data Synchronisation==: Keeping multiple copies of data in coherence with one another
- ==Process Synchronisation==: Multiple processes working together to achieve and overall purpose
	- This requires fast and reliable communication between the processes

In [[Distributed System]]s, we cannot assume these synchronisations

### Where is synchronisation needed?
Needed especially when...
- Multiple processes need to agree on ==ordering of events==
	- Was message m1 from process P sent before message m2 from process Q?
- Multiple processes simultaneously trying to ==access a shared resource== (can lead to [[Deadlock]])
	- e.g. printer which should grant temporary exclusive rights to users
