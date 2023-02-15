![[Pasted image 20221114182925.png]]
![[Pasted image 20221114182949.png]]

# Dynamic Array
An array which we reallocate when we run out of allocated memory and copy the old values to the newly allocated array
![[Pasted image 20221114183348.png]]

# Linked List
![[Pasted image 20221114183451.png]]
![[Pasted image 20221114183459.png]]

![[Pasted image 20221114183722.png]]

# Stack
**FILO** - First In Last Out
With a Dynamic Array we keep a pointer/index to the last added element and move it accordingly when we add to or remove from the stack
With a Linked list we simply add an element to the last pointed to element
![[Pasted image 20221114184444.png]]


# Queue
**FIFO** - First In First Out
With a queue we add and remove from different locations, with a stack we add and remove from the same location
With a dynamic array:
![[Pasted image 20221114184612.png]]
With a linked list:
![[Pasted image 20221114184723.png]]
now when we manipulate the linked list it's no longer an O(n) operation when we're doing queue operations because we already have a pointer to the back and front where we'll be manipulating the data


![[Pasted image 20221114185123.png]]
Linked list performs better here, while both have an O(n) upper bound, the linked list implementation can be constant time in the best case
![[Pasted image 20221114185248.png]]
