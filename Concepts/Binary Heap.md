### What is it?
- A binary heap is a special type of [[Binary Tree]] which:
	- Is a [[Complete Binary Tree]]
	- Satisfies the ==heap order property== invariant

|MIN Heap Order Property|MAX Heap Order Property|
|---|---|
|Each node’s value is **greater** than that of its parent| Each node’s value is **less** than that of its parent|

### Implementation
![[Pasted image 20230120120323.png]]
Can be implemented through arrays
![[Pasted image 20230120120349.png]]
Store the heapSize and length on the right hand side.

To access particular relations between nodes, where `i` is the index of a node:
- `parent(i)`
	- `i >> 1` or `floor(i/2)`
- `left(i)` (left child of i)
	- `i << 1` or `2*i`
- `right(i)`
	- `(i << 1) + 1` or `2*i + 1`
### Maintaining a Max Heap
Ensure that the max heap order property hasn't been violated:
- First assume left and right children are roots of valid max heaps
- From the root node, compare with children. If one of the children are greater than the root, swap the root with the largest child.
- Then run the same algorithm on the child node the swap occurred on.
```python
maxHeapify(H, i):  
	largest = i  
	l = H.left(i); r = H.right(i)

	if l < H.heapSize and H[l] > H[largest]:  
		largest = l

	if r < H.heapSize and H[r] > H[largest]:  
		largest = r  

	if largest != i  
		swap(H[i], H[largest])
		maxHeapify(H, largest)
```
### Building a Max Heap
- We can build a min/max heap from an existing array
- We do this by allowing values to 'bubble up' and 'bubble down'
1. First assume that bottom levels are valid max heaps
2. Use maxHeapify in a bottom-up manner
### Complexities
- **Space** - $O(n)$
- **Height** - $O(log(n))$
- **Building** - $O(n)$