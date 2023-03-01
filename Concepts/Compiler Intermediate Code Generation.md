### What is it?
A step in [[Compilers|compilation]]

- Translate language-specific constructs in the [[Abstract Syntax Tree (AST)]] into more general constructs.
- A criterion for the level of “generality”: it  should be straightforward to generate the target code from the intermediate representation chosen.
- Example of a form of IR (3-address code):
```
	tmp1=4
	tmp2=tmp1*a
	tmp3=tmp2*c
	tmp4=b*b
	tmp5=tmp4-tmp3
 ```
In the above example they've opted for 3 operands because it's quite close to a lot of architectures like ARM so it's easier to translate to it.

### Previous Phase
[[Compiler Semantic Analysis (Context Handling)]]

### Next Phase
[[Compiler Code Optimisation]]