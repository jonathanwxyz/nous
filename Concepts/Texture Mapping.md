#Visual-Computing 

### Image-Based
- the texture is defined by an image which modifies pixel colours
- This is the most common approach

#### Texture Coordinates
- For convenience, textures are defined with their own coordinate system
- Conventionally (u,v) or less commonly (s,t)
- Also see [[Texel]]s

#### Mapping texture per-polygon
![[Pasted image 20230406124328.png]]
- We associate (u,v) texture coordinates with each (x,y,z) vertex of a polygon  
- And interpolate the texture coordinates during scan-conversion  
- Then we blend the pixel colour with the texture colour

#### Performing texture mapping
- We do texture mapping as part of rasterisation
![[Pasted image 20230406124558.png]]

##### Seams
Often we can see seams in textures, one solution is to have textures that are seamless and one edge matches the other edge

#### Resolution mismatches
There are two cases of resolution mismatch:
- pixel resolution > texture resolution (i.e. pixels are smaller than texels).  
- pixel resolution < texture resolution (i.e. pixels are bigger than texels)

In each case we need to ==filter== aka ==sample==

##### pixel resolution > texel resolution
- Pixels A and B happen to map to the same texel, because pixel resolution > texel resolution
![[Pasted image 20230406125536.png]]
- We'll look at two approaches (there are more)
	1. no filter
	2. bilinear interpolation filter

###### No Filter
- We simply select the texel to which the pixel maps
- The result looks blocky
![[Pasted image 20230406125536.png]]
![[Pasted image 20230406125628.png]]

###### Bilinear Interpolation Filter
- We compute a texel colour from adjacent texels, averaging horizontally and  vertically
- ![[Pasted image 20230406130037.png]]

##### pixel resolution < texel resolution
- If pixel resolution < texel resolution, adjacent pixels may map to texels far apart in the texture, leading to missing detail, aka aliasing
- In animated sequences especially, we see unpleasant aliasing effects, as pixels “pop” on and off, or change colour unexpectedly in each frame
- ![[Pasted image 20230406130348.png]]
- There are a few techniques to alleviate this

###### Mipmap Filtering
- mip = multum in parvo (Latin), meaning “many things in a small place”
- The idea is simple: the further away from the viewpoint, the less detail we need
- So, we use a set of texture maps, and select which map to use, according to the distance of a pixel from the viewer
- ![[Pasted image 20230406130742.png]]
- Creating a mipmap:
	- ![[Pasted image 20230406130827.png]]
- When rendering we select one of the textures according to the distance of the pixel from the viewpoint
- Or, we can also choose the two closest textures, and do bilinear interpolation for extra smoothness
- ![[Pasted image 20230406130955.png]]
- ![[Pasted image 20230406131016.png]]
- ![[Pasted image 20230406131024.png]]

#### Textures as illumination
- Textures can be used to add accurate illumination to a real-time scene
- Off-line, pre-compute accurate diffuse illumination of the scene, using a global model (e.g., radiosity)
- Save rendered surfaces as textures – called lightmaps  
- In real-time, apply lightmap textures, and also actual surface textures.
- ![[Pasted image 20230406131157.png]]
- ![[Pasted image 20230406131209.png]]

#### Modelling rough surfaces
For this we use [[Bump Mapping]]

### Procedural
- a texture pattern is computed during rendering
- based on algorithms/rules, which modifies pixel colour
- Less common than [[#Image-Based]]