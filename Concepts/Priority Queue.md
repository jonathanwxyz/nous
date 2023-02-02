### What is it?
- A queue (FIFO, First in First Out), that also has some ==priority== associated with each element
- Elements with the highest priority are exited first

#### API
- `insert(k,e)` - push element e with key priority k
- `removeMax()` - pop element with the highest priority

### Implementation
Can implement efficiently using a Max [[Binary Heap]].
![[Pasted image 20230120123737.png]]
Highest priority is always at the root of the tree.

#### Removal
- Use the `removeMax()` method
- Remove from the root
- Swap last element into the root’s place (last element being the rightmost leaf)
- Use maxHeapify to “bubble-down” the swapped element, maintaining heap order property

#### Insertion
- Use the `insert(k,e)` method
- Insert at the next available insertion point
- Check against parent:  
	- Is there a violation of heap order property?  
	- If so, swap with parent