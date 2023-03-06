DFA - Deterministic Finite (State) Automata

![Untitled](Untitled%2011.png)

## DFA Diagram

![Untitled](Untitled%201%204.png)

This describes a switch of sorts that determines if a word composed of the symbols 0 and 1 has an odd or even number of 0s. The arrow on the left is the entry point. The two circles around the E (even) indicates which state it needs to be in in order for the criteria to be met.

![Untitled](Untitled%202%203.png)

This evaluates whether every third character is 0. For the first 2 characters we don’t care whether it is 0 or 1 so we denote that with 0,1. Then on the third character if it is a 1 then we go to state 4 and loop there forever, there aren’t two circles there because it isn’t an accepted state / it doesn’t satisfy what we want. If the third character is 0 then it loops back to keep checking future characters.

## Automata key

![Untitled](Untitled%203%203.png)

we must know what alphabet $\Sigma$ we are using.