![[Pasted image 20221023111224.png]]

![[Pasted image 20221023111337.png]]
If we change main.c we must update main.o and relink with the new main.o and the unchanged network.o and parser.o
If we change network.h we must recompile main.o and parser.o etc

![[Pasted image 20221023111514.png]]
We can use a Makefile to automate this process!
![[Pasted image 20221023111536.png]]
