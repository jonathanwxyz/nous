### Binary Multipliers
- A binary multiplier is an electronic circuit used in digital electronics to multiply two binary numbers.  
- It is built using binary [[Adders]].

#### Implementation
- Most techniques involve computing a set of partial products, and then summing the partial products together.
	- Multiply one input by each **digit** of the other  
		- easy in binary
	- **Shift** the partial products into the correct orientation
	- **Add** the justified partial products
	 - ![[Pasted image 20230102105723.png]]
- Plenty of opportunity for parallelism, as we can compute partial products simultaneously.
- Small multiplier blocks can be composed to make larger multipliers
	- ![[Pasted image 20230102110107.png]]
	- Used in [[Field-Programmable Gate Array (FPGA)|FPGA]] synthesis

### Hardware Implementation
- Uses [[Multi-Operand Adders]]