### What is it?
A step in [[Compilers|compilation]] in the [[Compiler Back-End]] phase.

- Map the [[Abstract Syntax Tree (AST)]] onto a linear list of target machine instructions in a symbolic form:
	- Instruction selection: a pattern matching problem.
	- Register allocation: each value should be in a register when it is used (but there is only a limited number): NP-Complete problem.
	- Instruction scheduling: take advantage of multiple functional units: NP-Complete problem.
- Target, machine-specific properties may be used to optimise the code.
- Finally, machine code and associated information required by the Operating System are generated.

### Previous Phase
[[Compiler Code Generation]]
