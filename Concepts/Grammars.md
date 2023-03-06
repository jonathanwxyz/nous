# Grammars
Grammars are an alternative way of defining languages

$\Sigma$ - Terminal symbols
$\Xi$  - Non Terminal symbols, contains special starting symbol

We create transitions where we convert our terminal symbols into terminal and non terminal symbols


![[Pasted image 20220308203137.png]]

Could write out like $A -> 0 | 1 | 2$ to make more concise

![[Pasted image 20220308203928.png]]

![[Pasted image 20220308214600.png]]
This grammar generates palindromes which aren't regular

TF, grammars allow us to construct non regular languages

![[Pasted image 20220308215513.png]]
Derive the transitions in the grammar by looking at the corresponding transitions in the DFA.
If a node is accepting, we add an $\epsilon$  

For every regular language, a grammar can generate it.

![[Pasted image 20220308215620.png]]