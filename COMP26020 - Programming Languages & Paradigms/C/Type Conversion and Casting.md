![[Pasted image 20221023112052.png]]
![[Pasted image 20221023112153.png]]

![[Pasted image 20221023112656.png]]
Here the signed int is promoted to the unsigned int, it doesn't change the bits so what was -1 as an int is now the max value of an unsigned int (around 4 billion). so si < ui evaluates to false.
BE CAREFUL!!!

![[Pasted image 20221023112938.png]]
Overflow!

![[Pasted image 20221023113030.png]]

![[Pasted image 20221023113135.png]]

![[Pasted image 20221023113318.png]]
The bottom example fixes the similar example above

![[Pasted image 20221023113434.png]]
