
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

### Previous Phase
[[Compiler Lexical Analysis (Scanning)]]

### Next Phase
[[Compiler Semantic Analysis (Context Handling)]]