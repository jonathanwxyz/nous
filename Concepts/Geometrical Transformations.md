#Visual-Computing 

In order to represent all of the transformations below, in computer graphics [[Homogeneous Coordinates]] is used.

▪ Define geometry as sets of vertices
▪ Apply transformations to vertices to change them  
▪ Examples: translation, scaling, rotation  
▪ To transform a whole shape, we transform all its vertices
![[Pasted image 20230214130207.png]]

### Translation
![[Pasted image 20230214130226.png]]
Apply a shift to all coordinates
![[Pasted image 20230214130242.png]]

### Scaling
![[Pasted image 20230214130312.png]]
Apply a 3D scale to all coordinates
![[Pasted image 20230214130259.png]]

### Rotation (2D)
- We want to rotate point P about the origin, by angle θ
![[Pasted image 20230214130500.png]]
==Important==
- x= RcosΦ  
- y= RsinΦ  
- x’= Rcos(θ+Φ)  
	- x’= RcosΦcosθ - RsinΦsinθ  
- y’= Rsin(θ+Φ)  
	- y’= RcosΦsinθ + RsinΦcosθ  
- Substituting for RcosΦ and RsinΦ gives:
> -  x’= xcosθ – ysinθ  
> -  y’= xsinθ + ycosθ
![[Pasted image 20230214130659.png]]

What about rotating about a point other than the origin?
Translate to the origin (-qx,-qy), apply the rotation, translate back again (+qx,+qy)
![[Pasted image 20230214130858.png]]

### Rotation (3D)
#### Rotating about a particular axis (e.g Z axis)
Same as 2D
- x’= xcosθ – ysinθ  
- y’= xsinθ + ycosθ  
- z’= z (no change)
![[Pasted image 20230214131438.png]]

#### Rotating about an arbitrary vector
More involved, we must utilise [[Homogeneous Coordinates#^dd2051|composite transformations]]  
The steps are described [[Rotating about an arbitrary vector|here]]