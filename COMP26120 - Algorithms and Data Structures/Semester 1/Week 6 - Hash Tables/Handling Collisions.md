# Separate Chaining
Complexity can approach linear, especially if we have a poor hash function (doesn't uniformly map elements)

# Open Addressing
![[Pasted image 20221114194030.png]]

## Linear Probing
If a slot is already taken by a value, iterate the index by 1 until there's an empty slot to fill
![[Pasted image 20221114194653.png]]

## Quadratic Probing
If a slot is already taken by a value, iterate the index by i^2 where i is how many steps we've taken until there's an empty slot to fill
![[Pasted image 20221114194820.png]]

## Double Hashing
![[Pasted image 20221114195032.png]]
If there's a collision we apply a second hashing function to work out an offset
