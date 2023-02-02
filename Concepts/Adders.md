### Ripple Carry (RCA)
![[Pasted image 20230101142654.png]]
- Simple, small (cheap), but relatively slow (long [[Critical Path]]).
- Made by chaining [[Full Adder]]s.
- Each stage must wait until the previous carry bit has been calculated to begin calculating it's own sum and carry bit

### Carry Look Ahead (CLA) or Fast Adder
![[Pasted image 20230101142853.png]]
- Improves speed by reducing the amount of time required to determine carry bits compared to the RCA.
- Calculates one or more carry bits before the sum
- This reduces the wait time to calculate the result of the larger-value bits of the adder.