### What is it?
A step in [[Compilers|compilation]] in the [[Compiler Front-End|front-end]].
In this step we take the human readable source code and make it easier for computers to parse

### Steps
- Reads characters in the source program and groups them into words (basic unit of syntax)
- Produces words and recognises what sort they are.
- The output is called token and is a pair of the form <type, lexeme> or <token_class, attribute>
- E.g.: a=b+c becomes <id,a> <=,> <id,b> <+,> <id,c>
- Needs to record each id attribute: keep a symbol table.
- Lexical analysis eliminates white space, etc…
- Speed is important - use a specialised tool: e.g., flex - a tool for generating scanners: programs which recognise lexical patterns in text; for more info: % man flex

### Next Phase
[[Compiler Syntax Analysis (Parsing)]]