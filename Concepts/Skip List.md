### What is it?
- A linked list that has nodes of variable size (1 to $O(log(n)$)), not all nodes are connected to each other allowing for skipping over nodes in traversing the data structure.
- Randomised data structure (height of a node is random)
- Generalisation of a sorted linked list
- Allows to skip over many items, making it efficient
![[Pasted image 20230121165916.png]]

### Searching
```python
def find(k):  
	if (k == key):
		DONE  
	else if (k >= next key):
		Go right  
	else if (k < next key):
		Go down
```
- Skip over as much as possible:  
	- If the next key is less than (or equal) to my search, I can skip over the elements  
	- If not, then I have to go down a level

### Insertion
- Search for the space where the number to be inserted should be
- Insert it
- Flip coin to decide height
- Fix pointers
	- Use an array of where we “downward transitioned”
	- Stack is good – just pop the first X off the top
![[Pasted image 20230121170412.png]]

### Complexity
- **Search**
	- Worst - $O(n + h)$
		- All n towers are h high
		- We know h is in $O(log(n))$
	- Average - $O(log(n))$
		- We must go down the entire skip list $O(log(n))$
		- We encounter expectedly 2 elements per level
- **Space**
	- $O(n)$
	- Elements present at each level - $\frac{n}{2^i}$
	- Then summed up from i=0 to h
