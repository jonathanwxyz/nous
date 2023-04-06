#Visual-Computing 

Phon (aka normal vector) Shading is a sophisticated form of shading. More sophisticated than [[Gouraud Shading]] in that instead of interpolating colours, we ==interpolate normal vectors along the scanline== and compute illumination (for example [[Local Illumination]]) for every pixel.

### Algorithm
![[Pasted image 20230404142929.png]]
- for each scanline {  
	- compute average normal NLeft from NA and NC  
	- compute average normal NRight from NB and NC  
	- average between NLeft and NRight along the scanline, and compute colour C using illumination model  
}

### Results
![[Pasted image 20230404143102.png]]
As we can see, Phong has the superior result, it has better specular reflection and detail. However it comes at [[Shading Surfaces#Rendering Expense|greater expense.]]