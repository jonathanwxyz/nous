### What is it?
Takes a program written in one language (==Source Program==) and translates it into another language (==Target Language==).
![[Pasted image 20230301104652.png]]
The key principle underlying all compiler technology is: Ability to extract properties of a source program (analysis) and transform it to construct a target program (synthesis)

### Examples of Compilation
- C++ to ARM
- C++ to C
- LaTeX to PDF
- High Performance Fortran (HPF) to Fortran (parallelising compiler)
- Java to Bytecode (The bitecode is then ==interpreted==)

### Difference to Interpreters?
There's a difference between compiled languages where we take the whole source program and compile it (like C), and interpreted languages where we take the source code line by line, interpret it and execute it (like Python and PHP). They have a lot of commonalities in terms of the steps involved but should be seen as distinct

### Principles of Compilation
The compiler must:
- Preserve the meaning of the program being compiled
- "improve" the source code in some way

There are other more situational things that the compiler might need to specialise for:
- Speed
- Debugging
- Size (embedded)
- Feedback
- Fast compilation
In general it's impossible to have all of these things at the same time. ==Tradeoffs==.

Qualities we want:
- generates correct code (first and foremost!)
- generates fast code
- conforms to the specifications of the input language
- copes with essentially arbitrary input size, variables, etc.
- compilation time (linearly)proportional to size of source
- good diagnostics
- consistent optimisations
- works well with the debugger

### Steps
1. [[Compiler Lexical Analysis (Scanning)]]
2. [[Compiler Syntax Analysis (Parsing)]]
3. [[Compiler Semantic Analysis (Context Handling)]]
4. [[Compiler Intermediate Code Generation]]
5. [[Compiler Code Optimisation]]
6. [[Compiler Code Generation]]

### Front End and Back End
![[Pasted image 20230301111017.png]]
In compilers there are 2 main steps called the [[Compiler Front-End|front end]] and the [[Compiler Back-End|back end]].
In between these steps is an ==Intermediate Representation (IR)== which allows for the components to be swapped out and for communication to be possible.
![[Pasted image 20230301110917.png]]
- All language specific knowledge must be encoded in the front-end
- All target specific knowledge must be encoded in the back-end
But: in practice, this strict separation is not free of charge.

### General Structure
![[Pasted image 20230301112100.png]]

### Useful Definitions
[[Compiler Useful Definitions]]