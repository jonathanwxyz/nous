#Visual-Computing 

![[Pasted image 20230216162027.png]]
- The ==surface normal== is the vector perpendicular to the plane of the polygon
- We can use this to distinguish the 'front' and the 'back'
	- surface vector coming out of the front
- Describes the ==orientation== in 3D space
- Orientation is an essential property used extensively in lighting calculations, collisions, culling...

### Finding the Surface Normal
![[Pasted image 20230216163451.png]]
1. Choose a pair of sequential edges E1 and E2 and compute their vectors  
2. Invert the direction of the first so they now emanate from their shared vertex
3. Their [[Cross Product (Outer Product)]] gives the surface normal N
	1. ![[Pasted image 20230216163710.png]]
 4. We then almost always normalize N (make its length 1)
