#Visual-Computing 

### Planar Projections
Here we project lines to lines

There are 2 classes of planar geometric projection:
- Parallel projection
- Perspective projection
- ![[Pasted image 20230303171441.png]]

#### Parallel Projection
![[Pasted image 20230303172037.png]]
Centre of projection, or “eye point”, is at infinity, so projectors are parallel

##### Orthographic views
![[Pasted image 20230303172121.png]]
- In orthographic parallel projection, projectors are perpendicular to the projection plane  
- The projection plane is parallel to a plane (XY, XZ, YZ) of the world  
- The projected image shows only 2 of the 3 axes  
- There is no distortion of lengths or angles, so useful for CAD

###### In OpenGL
![[Pasted image 20230304153325.png]]

##### Computing orthographic projection
For projecting onto z=0 simply do a transformation where we set the z component of 3d points to 0
![[Pasted image 20230303172509.png]]
![[Pasted image 20230303172526.png]]
- This is a singular operation (no inverse / not reversible)

##### Axonometric projections
![[Pasted image 20230303172654.png]]
- In axonometric parallel projection, projectors are perpendicular to the projection plane  
- The projection plane can have any orientation  
- Now we can see the 3 axes. Distortion of lengths or angles, but measurements can still be made

##### Oblique projections
- This is the most general case of parallel projection  
- Projectors can make any angle with the projection plane  
- The projection plane can have any orientation relative to the object being viewed  
- We see the three axes. There is distortion of lengths or angles, but measurements can still be made  
- We can of course derive matrices to perform all the parallel projections we have seen
![[Pasted image 20230303173140.png]]

##### View volume
![[Pasted image 20230304152826.png]]
- For parallel orthographic projection, it’s a cuboid  
- The cuboid is defined by a near plane (the projection plane) and a far plane, and top/bottom, left/right planes  
- The near and far planes are orthogonal to the camera’s $\hat{F}$ axis

#### Perspective projection
![[Pasted image 20230303173804.png]]
So everything comes to a point ==the projectors converge==, in comparison to parallel projection where it's eternally parallel

![[Pasted image 20230303174053.png]]
Objects further away from the Centre Of Projection (COP) become smaller. Edges that were parallel may converge. Angles between edges may be distorted.
![[Pasted image 20230303174222.png]]
These parallel planks appear to be converging, this is just an illusion of perspective

![[Pasted image 20230303174258.png]]
Distance objects appear smaller in the projected image. Are objects small or far away?

![[Pasted image 20230303174430.png]]
Which (XY, XZ, YZ) planes of the world are parallel to the projection plane determines how many vanishing points are seen in the projected image  
- 2 of (XY, XZ, YZ) are parallel: 1-point perspective  
- 1 of (XY, XZ, YZ) are parallel: 2-point perspective  
- 0 of (XY, XZ, YZ) are parallel: 3-point perspective

##### Computing Perspective
![[Pasted image 20230303175027.png]]
Projection plane at z=d, parallel to the XY plane.

![[Pasted image 20230303175241.png]]
![[Pasted image 20230303175258.png]]
This is for 1-point projection

for 3 point:
![[Pasted image 20230303175500.png]]

###### A problem with this:
As this is a singular operation, we lose information about the Z axis (depth). So we don't know how close objects are to the camera and thus can't do hidden surface removal

###### Solution: Projection Normalisation
![[Pasted image 20230304153650.png]]
- We need a perspective transformation which preserves depth information.  
- Suppose we have a particular perspective transformation expressed by frustum F and matrix M  
- It can be shown that we can derive a new transformation matrix PN, based on M, that ==distorts F into a cube  ==
- Transforming our model by PN, and then taking an [[#Computing orthographic projection|orthographic projection]]...
- ...==produces exactly the same result== as performing our original perspective transformation M, with one difference: the z depth values are preserved  
- This new technique is called ==projection normalization==, and OpenGL creates PN for us automatically.

##### View volume
![[Pasted image 20230304153141.png]]
- For perspective projection, this view volume is a frustum, a truncated pyramid  
- The frustum is defined by a near plane (the projection plane) and a far plane  
- The near and far planes are orthogonal to the camera’s $\hat{F}$ axis

##### Perspective Projections in OpenGL
![[Pasted image 20230304153408.png]]
