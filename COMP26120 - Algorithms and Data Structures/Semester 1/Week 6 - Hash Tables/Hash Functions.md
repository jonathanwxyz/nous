**Hash Codes** - Maps the data to an integer
**Compression** - Placing the hash codes into categories of a given range
![[Pasted image 20221114192009.png]]
![[Pasted image 20221114192017.png]]
![[Pasted image 20221114192313.png]]
mod N is a common compression strategy
![[Pasted image 20221114192356.png]]
![[Pasted image 20221114192807.png]]
![[Pasted image 20221114192858.png]]

## Hash Codes
To determine the hash code of a string we might want to sum the characters or do an XOR however this yields collisions in the case of symmetrical strings like tab and bat
![[Pasted image 20221114193211.png]]

![[Pasted image 20221114193404.png]]