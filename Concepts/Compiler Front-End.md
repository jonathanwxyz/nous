![[Pasted image 20230301111012.png]]
### What is it?
The first big step in [[Compilers|compilation]].
==Front-end== performs the ==analysis== of the source language:
- Recognises legal and illegal programs and reports errors.
- “understands” the input program and collects its semantics in an Intermediate Representation (IR).
- Produces IR and shapes the code for the back-end.
- Much can be automated.

After the IR is produced it can then be fed into the [[Compiler Back-End]]

### Complexity
Typically O(n), meaning the complexity is in proportion to the amount of source code.

### General Structure
![[Pasted image 20230301112021.png]]
1. [[Compiler Lexical Analysis (Scanning)]]
2. [[Compiler Syntax Analysis (Parsing)]]
3. [[Compiler Semantic Analysis (Context Handling)]]
4. [[Compiler Intermediate Code Generation]]