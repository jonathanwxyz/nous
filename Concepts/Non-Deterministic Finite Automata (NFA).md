[[Deterministic Finite Automata (DFA)]] has a function that describes a transition, for each state and character in the alphabet there is one state we can move to.

With NFAs there may be several such states. Put another way there can be more than 1 transition out of a state on the same input symbol. In which case we must track both possibilities.

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled.png)

Describe words who’s second last letter is an ‘a’

This is problematic in DFAs because there are 2 ways we could go from the first node if there’s an ‘a’ so it is no longer a function

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled%201.png)

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled%202.png)

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled%203.png)

We check all possibilities when there’s multiple paths

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled%204.png)

Transition Relation rather than function (DFA)

![Untitled](images/V3%20-%20NFA%20D%20a8d47/Untitled%205.png)