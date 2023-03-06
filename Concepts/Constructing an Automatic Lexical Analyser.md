This relates to [[Compiler Lexical Analysis (Scanning)#Automatic Lexical Analysis]].

### How can we convert a specification into code?
- Write down the [[Regular Expressions|RE]] for the input language.
- Convert the RE to a [[Non-Deterministic Finite Automata (NFA)]]([[RE to NFA - Thompson’s construction]])
- Build the [[Deterministic Finite Automata (DFA)]] that simulates the NFA ([[NFA to DFA - subset construction]])
- Minimise the DFA ([[DFA Minimisation - Hopcroft’s algorithm]])

The tables generated through this method can become really large, so for high performance best ==encode states and actions in the code automatically==
e.g.
Register -> r digit digit*
```c
       word=‘’; char=‘’; goto s0;
   s0: word=word+char;
       char=input_char();
       if (char == ‘r’) then goto s1 else goto error;
   s1: word=word+char;
       char=input_char();
       if (‘0’ <= char >= ‘9’) then goto s2 else goto error;
   s2: word=word+char;
       char=input_char();
       if (‘0’ <= char >= ‘9’) then goto s2 
          else if (char== EOF) return acceptance 
               else goto error
error: print “error”; return failure;
```
The code generated will be spaghetti code however we don't really care as we gain efficiency as there are fewer operations and avoids memory operations, and as it's generated automatically no one needs to really see it.