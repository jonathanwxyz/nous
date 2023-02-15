#Visual-Computing 

A way of being able to do [[Geometrical Transformations]] through only [[Matrix]] multiplication

- In order to use a consistent matrix representation for all kinds of linear transformations, we’ve had to add an extra coordinate, w, to our usual 3D coordinate (x,y,z)
- Usually w = 1, if it isn't we normalise the matrix so that it is (divide throughout by w)

### 3D Scaling
![[Pasted image 20230214133026.png]]

### 3D Translation
![[Pasted image 20230214133044.png]]
![[Pasted image 20230214133259.png]]

### 3D Rotation
#### about x axis
![[Pasted image 20230214133111.png]]

#### about y axis
![[Pasted image 20230214133148.png]]

#### about z axis
![[Pasted image 20230214133201.png]]

#### about an arbitrary vector
described [[Rotating about an arbitrary vector|here]]

### Composite Transformations

^dd2051

If we now apply a transformation to P' we have:
![[Pasted image 20230214133658.png]]
This is equivalent to multiplying the transformations you want to apply then multiply this composite transformation with the original vector
![[Pasted image 20230214133707.png]]

This is ==Non-Commutative==, the order in which you apply transformations does matter

Example:
2d scaling by (sx, sy)
we first want to apply a translation to bring the object to the origin M1
then apply the scaling M2
then apply the opposite translation M3
we can do this all in one transformation by computing Mc = M3 . M2. M1

### Inversions
![[Pasted image 20230214134733.png]]
Matrix A and B are [[Matrix Inverses|inverses]] of each other

### Non-Invertible Transformations
![[Pasted image 20230214135709.png]]
The transformation here cannot be undone
