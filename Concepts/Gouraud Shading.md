#Visual-Computing 

Gouraud (aka intensity shading) uses interpolation to smooth out the discontinuities between the polygons.
![[Pasted image 20230404141722.png]]
![[Pasted image 20230404141734.png]]
- We can approximate the normals of the underlying “surface” the polygons are modelling
- by [[Averaging Vertex Normals|averaging the normals where polygons share vertices]]

### Gouraud Algorithm
![[Pasted image 20230404142004.png]]
- compute average vertex normals at A, B and C  
- compute pixel colours C A, C B , C C  
- for each scanline {  
	- average colour C Left from C A and C C  
	- average colour C Right from C B and C C  
	- average between C Left and C Right along the scanline  
}

### Results
![[Pasted image 20230404142201.png]]
- Better than [[Flat Shading]], but we lose a lot of [[What are Diffuse and Specular Reflection?#Specular|specular reflection]], 
- and we can notice the silhouette edges, still polygonal
- Also some Mach banding
- Sometimes edges are "shaded away" as the vertices are averaged out, for example the sharp edges of a cube might disappear
	- ![[Pasted image 20230404142658.png]]
	- Edges must be tagged in a data structure to avoid interpolation across it

### Optimisations
![[Pasted image 20230404142331.png]]
Here we just calculate the increment once and then apply this as we go from C left to C right.
We can similarly compute C left and C right in an incremental fashion

