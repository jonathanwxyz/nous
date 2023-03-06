### What is it?
A step in [[Compilers|compilation]] in the [[Compiler Front-End|front-end]] phase.

In this step we take the human readable source code and make it easier for computers to parse. This is done by reading characters and producing sequences of tokens.

### Steps
- Reads characters in the source program and groups them into words (basic unit of syntax)
- Produces words and recognises what sort they are.
- The output is called token and is a pair of the form <type, lexeme> or <token_class, attribute>
- E.g.: a=b+c becomes <id,a> <=,> <id,b> <+,> <id,c>
- Needs to record each id attribute: keep a symbol table.
- Lexical analysis eliminates white space, etc…
- Speed is important - use a specialised tool: e.g., flex - a tool for generating scanners: programs which recognise lexical patterns in text; for more info: % man flex

### Building a Lexical Analyser by hand
This is a cumbersome task which is is difficult to modify and generally not recommended. It may look something like this:
```c
void get_next_token() {
	c=input_char();
	if (is_eof(c)) { token  (EOF,”eof”); return}
	if (is_letter(c)) {recognise_id()}
	else if (is_digit(c)) {recognise_number()}
		 else if (is_operator(c))||is_separator(c))
			{token <- (c,c)}  //single char assumed
			else {token  (ERROR,c)}
	return;
}
...
do {
	get_next_token();
	print(token.class, token.attribute);
} while (token.class != EOF);
```

### Automatic Lexical Analysis
Preferred to doing it manually, it can be done through using [[Regular Expressions]]. Visually we can represent these RegExps as [[Deterministic Finite Automata (DFA)]] like:
![[Pasted image 20230301145848.png]]
which corresponds to: 
`Register -> r (0|1|2|…|9) (0|1|2|…|9)*`

Computationally these ==transition diagrams== can be represented as a ==transition table==
![[Pasted image 20230301150059.png]]

If we know the transition table and the final state(s) then building a lexical analyser is as simple as running this piece of code:
```c
char=input_char(); 
state=0;    // starting state
while (char != EOF) {
    state <- table(state,char);
    if (state == ‘-’) return failure;
    word=word+char;
    char=input_char();
}
if (state == FINAL) return acceptance; else return failure;
```

The theme of [[Constructing an Automatic Lexical Analyser]] is discussed here.

### Practical Considerations
#### Language design altered by lexical analysis
DO5I=1,25 vs DO5I=1.25 (Fortran: urban legend has it that an error like this caused a crash of an early NASA mission)
The former was a do loop from i = 1 to 25 and until the statement marked with 5, the latter is a variable called DO5I assigned 1.25.
Modern languages make easy mistakes like this much harder thanks to more considerate lexical analysis.

#### Role of lexical analysis
Take the C++ example `aaaa<mytype<int>>`, the `>>` at the end as 2 consecutive symbols (as `>>` can be used for stream operations). The confusion will only be resolved by the [[Compiler Syntax Analysis (Parsing)|parser]].

### Tools for Generating Lexical Analysers
- [[(F)lex]]

### Next Phase
[[Compiler Syntax Analysis (Parsing)]]