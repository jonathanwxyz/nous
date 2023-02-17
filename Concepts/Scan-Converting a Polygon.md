- Here we convert the geometry of a [[OpenGL Polygons|polygon]] into pixels on a screen. There are many ways to do this.
- The polygon has been transformed by the viewing pipeline, so we know its (x,y,z) vertex coordinates in screen space
- The (x,y) coordinates corresponds to a pixel position
- The z coordinate is a measure of the vertex’s distance from the eye (or "camera").

### Naive approach
Essentially work out the [[Scan-Converting a Line]] for each of the edges then colour in  the middle![[Pasted image 20230216172544.png]]
![[Pasted image 20230216172555.png]]
There are more efficient methods that are actually used

### Sweep Line Algorithm
[[Sweep-Line Algorithm]]