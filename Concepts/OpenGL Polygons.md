#Visual-Computing 

In [[OpenGL]], polygons are defined by their vertices (the points/corners) ![[Pasted image 20230216161555.png]]
So a polygon is a shape within given vertices.

Specifically OpenGL needs ==Convex== Polygons (interior angles less than 180 degrees)

If we have concaved polygons we must process them to make them compatible:
![[Pasted image 20230216161838.png]]
GLU provides functions to tessellate these polygons.

### Attributes (IMPORTANT)
- [[Surface Normal]]
