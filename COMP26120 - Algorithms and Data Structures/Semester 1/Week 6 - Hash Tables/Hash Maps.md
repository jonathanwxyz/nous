![[Pasted image 20221114190353.png]]
- In the case of the tiger we had a **collision** but we decided to utilise **separate chaining** where we put them in the same category.
- In the case of the Elephant we also had a collision but in this case we utilised **open addressing** to place it in an empty category.
	- Specifically we used **linear probing** where we'd increment the categories until we found an empty one.
![[Pasted image 20221114191211.png]]
- Lookup table alone has the risk of having out of bounds errors so we need hashing to keep the elements within the bounds of the array.
- Lookup table + Hashing has the problem of when we have multiple elements mapping to the same array index, in this case we need separate chaining which is a linked list
- If loads of elements get mapped to one index then that's a sign of a bad hash algorithm

![[Pasted image 20221114191617.png]]
![[Pasted image 20221114191634.png]]
