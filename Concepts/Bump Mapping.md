#Visual-Computing 

### Why do rough surfaces look rough?  
![[Pasted image 20230406131308.png]]
- The surface normals change across the bumps, so the top of the bumps appear brighter than the sides

### Bump Mapping
- Rather than alter the surface colour, as in texturing, we can alter the surface normal  
- this has the same effect on the illumination model as if the surface were really geometrically different (but it isn’t)
![[Pasted image 20230406131437.png]]

### Altering a surface normal
1. Introduce two unit vectors $\hat{N}_U$ and $\hat{N}_V$ each orthogonal to the surface normal
	- ![[Pasted image 20230406131610.png]]
2. Scale $\hat{N}_U$ and $\hat{N}_V$ by $b_U$and $b_V$
	- To give the "bump vectors"
	- ![[Pasted image 20230406131734.png]]
3. Add the bump vectors to the original surface normal to get an altered surface normal
	- $N' = \hat{N} + (b_U\hat{N}_U + b_V\hat{N}_V)$
	- ![[Pasted image 20230406131911.png]]

### Bump mapping example
![[Pasted image 20230406131945.png]]

### Where do we get $b_U$ and $b_V$?
- One way is to use a texture as a bump map to derive bU and bV  
- We use the texel colours to encode bumpiness

- We treat the value of each texel as a "height" which will control the bumpiness of the surface
- We can say that brighter texels are "higher" than darker [[Texel]]s
- ![[Pasted image 20230406132144.png]]
- For each texel T, we compute its x and y brightness gradients and use them as bU and b V:
![[Pasted image 20230406132234.png]]
