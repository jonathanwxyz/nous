(also known as shift registers)

### How it works
- A cascade of [[Flip-flop]]s sharing the same clock
- The output of a flip-flop is connected to the data input of the next flip-flop, creating a chain
- Creates a circuit that shifts by one position the "bit array" stored in the shifter

### Useful for
- [[Multipliers|Multiplication]]
- Division
- Aligning and assembling bit fields into longer words

### One-place shifter
![[Pasted image 20230102111507.png]]

### Bi-directional shifter
Shifts multiple places at 1 shift per cycle
![[Pasted image 20230102111604.png]]

### Barrel shifter
![[Pasted image 20230102111625.png]]
- Shifts arbitrary number of places in one operation
- Expensive in wiring

##### Definition
A barrel shifter is a digital circuit that can shift a data word by a specified number of bits without the use of any sequential logic, only pure combinational logic.

##### Implementation
One way to implement it is as a sequence of multiplexers where the output of one  
multiplexer is connected to the input of the next multiplexer in a way that depends on the shift distance.

##### Uses
- Often used to shift and rotate n-bits in modern microprocessors, typically within a single clock cycle.
- ==hardware implementation== of [[Floating Point Arithmetic]].
	- For **add** and **sub**, the mantissas must be aligned
		- Requires shifting the small number to the right until the exponents match
		- Done by subtracting the exponents, and shifting that number of places
		- Note, with a simpler shifter it would take n clock cycles.
