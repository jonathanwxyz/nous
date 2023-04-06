
### What is it?
A step in [[Compilers|compilation]] in the [[Compiler Front-End|front-end]] stage.
In this step we ensure that the code is syntactically valid code by producing a tree with a grammar using the code provided, if it's impossible to produce a tree then it's invalid syntax.

### Steps
- Imposes a hierarchical structure on the token stream.
- This hierarchical structure is usually expressed by recursive rules.
- Context-free grammars formalise these recursive rules and guide syntax analysis.
- Example:
```Haskell
	expression -> expression ‘+’ term | expression ‘-’ term | term
	term -> term ‘*’ factor | term ‘/’ factor | factor
	factor -> identifier | constant | ‘(‘ expression ‘)’
```
(this grammar defines simple algebraic expressions)

With these grammars we produce a parse tree and then an [[Abstract Syntax Tree (AST)]]

We use [[Context-free Grammars]] rather than regular expressions because REs can't be used for things like balanced or nested brackets, or for an equal number of a certain character followed by the same number of a different character. The hierarchy of grammars is explored more in [[Chomsky's Hierarchy of Grammars]]

If a grammar can produce a more than one parse tree for some sentence then it is ==ambiguous==. This is a problem for programming languages as it makes the desired functionality unclear.
- lefmost derivation: CFG derivation by changing the non terminal symbols left to right
- rightmost derivation: CFG derivation by changing the non terminal symbols right to left

There are 2 main ways for computers to do this parsing [[Context-free Grammars#Top-Down Parsing]]


### Previous Phase
[[Compiler Lexical Analysis (Scanning)]]

### Next Phase
[[Compiler Semantic Analysis (Context Handling)]]