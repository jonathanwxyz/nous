#Visual-Computing 

- Viewing the world from a particular viewpoint, which parts of the world can we see, and which parts can we not see, because other objects block them?  
- There are two fundamentally different approaches to solving this problem:  
	- Work in ==3D world space==. We work it out geometrically in 3D, and then draw the result. This was the first approach used, 1960-1980s, and it is extremely hard  
	- Work in ==2D display space==. During scan-conversion, whenever we generate a pixel P, we determine whether some other 3D object, nearer to the eye, also maps to P. This is now the standard approach.
		 - For each shared pixel we only represent the closest one to the camera

### Algorithms
- [[The Z-Buffer]]