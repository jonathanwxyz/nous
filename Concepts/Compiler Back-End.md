### What is it?
![[Pasted image 20230301111020.png]]
The second big step in [[Compilers|compilation]] where the Back-end does the target language synthesis:
- Chooses instructions to implement each Intermediate Representation (IR) operation.
- Translates IR into target code.
- Needs to conform with system interfaces.
- Automation has been less successful.

### Complexity
back-end is NP-complete, meaning we don't know how to solve in less than exponential time. For this reason ==heuristics== are used

### General Structure
![[Pasted image 20230301112039.png]]
1. [[Compiler Code Optimisation]]
2. [[Compiler Code Generation]]