The arithmetic operations below are performed on [[Floating Point Numbers]].

### Multiplication
![[Pasted image 20221227151620.png]]
- [[Floating Point Numbers#^5d9f91|Mantissas]] are multiplied
- [[Floating Point Numbers#^3702b8|Exponents]] are added
	- Beware of range over or under flows
 - [[Floating Point Numbers#^b24e41|Sign]] bits are XORed
	 - minus (1) minus makes a plus
	 - plus (0) plus makes a plus
	 - plus minus makes a minus
	 - minus plus makes a minus
- renormalising takes extra steps (12.08E12 -> 1.21E13)

### Division
- Similar but subtract the Exponents

### Addition / Subtraction
- Can only add/sub when the exponents are equal
- Mantissa of smaller value must be shifted right until exponents are equal
- Then mantissas are added or subtracted depending on operation and sign bits
- Result may need renormalising

> ### Floating Point Arithmetic is not [[Associativity|Associative]]!
