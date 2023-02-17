#Visual-Computing 

Also known as the Depth-Buffer (Z axis is depth). This is a technique for [[Hidden Surface Removal]].

- We introduce a new data structure called the Z-buffer  
- For every pixel in the display memory, there is a corresponding entry in the Z-buffer  
- The Z-buffer is used to keep a record of the z-value of each pixel
![[Pasted image 20230216173403.png]]

### Algorithm
1. Initialise each pixel to desired background colour  
2. Initialise each Z-buffer entry to MAXDEPTH (biggest possible number)  
3. For each pixel P generated during scan-conversion of an object:  
	 ```c
	 IF z-coordinate of P < Z-BUFFER[P] THEN  
	// i.e., the part of the 3D object that mapped to P  
	// is nearer to the eye than any other part of the world  
	// that has so far mapped to P  
	Compute colour of P // lighting, texture... later in the course  
	Store colour in P  
	Store (i.e., update) z-coordinate of P in Z-BUFFER[P]  
	ELSE  
	// something else has already mapped to P and is nearer to us  
	// so don’t change P
￼-	```

### Z fighting
When there are 2 surfaces close to each other, rounding errors can cause surfaces to have 'stitching'
![[Pasted image 20230216174122.png]]
- Lack of precision in the Z-buffer leads to incorrect rendering of pixels with similar z- values  
- Especially horrible when animated
- Solution: glPolygonOffset()
