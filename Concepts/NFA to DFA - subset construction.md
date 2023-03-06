### What is it?
An algorithm for turning [[Non-Deterministic Finite Automata (NFA)]] to [[Deterministic Finite Automata (DFA)]].

### Two key functions
1. move(si,a): the (union of the) set of states to which there is a transition on input symbol a from state si
2. $\epsilon$-closure(si): the (union of the) set of states reachable by $\epsilon$ from si.

### The algorithm
- start with the $\epsilon$-closure of the starting state from NFA.
- repeat for the set of states you find and any new one: 
	- for each symbol take their $\epsilon$-closure(move(state,symbol))

### Example: NFA for (a | b)\*abb
![[Pasted image 20230303141354.png]]
Result:
![[Pasted image 20230303141429.png]]
