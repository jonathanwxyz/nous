We need generics so that we don't have to rewrite code for different datatypes that conceptually do the same:
![[Pasted image 20221118124746.png]]
![[Pasted image 20221118124636.png]]
![[Pasted image 20221118124656.png]]

# Templates
![[Pasted image 20221118125941.png]]
when calling the function we use angle brackets: `min<int>(x, y)` Although often this can be inferred so we just do `min(x,y)`
The functions created by the compiler have 0 overhead and are just as fast as writing by hand.
![[Pasted image 20221118130120.png]]
![[Pasted image 20221118130152.png]]
![[Pasted image 20221118130205.png]]
