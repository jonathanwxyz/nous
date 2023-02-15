![[Pasted image 20221114180233.png]]
![[Pasted image 20221114181554.png]]

![[Pasted image 20221114181617.png]]
in this case because we must define s1 as a shape rather than as a circle or rectangle when we call getArea on the object it uses the default getArea defined in shape (which is not useful) even though the underlying object is actually a circle or rectangle.
- Use `virtual` when declaring the methods to get around this and use `override` when implementing the method
![[Pasted image 20221114181855.png]]
![[Pasted image 20221114181914.png]]
