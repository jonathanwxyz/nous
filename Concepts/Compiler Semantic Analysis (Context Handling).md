### What is it?
A step in [[Compilers|compilation]] in the [[Compiler Front-End|front-end]] stage.
- Collects context (semantic) information, checks for semantic errors, and annotates nodes of the tree with the results.
- Examples:
	- type checking: report error if an operator is applied to an incompatible operand.
	- check if a variable is properly declared.
	- name-related checks.

### Previous Phase
[[Compiler Syntax Analysis (Parsing)]]

### Next Phase
[[Compiler Intermediate Code Generation]]