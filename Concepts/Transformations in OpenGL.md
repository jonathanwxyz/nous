This builds on top of content from [[Homogeneous Coordinates]] and [[Geometrical Transformations]]
- OpenGL maintains two transformation matrices internally:  
	- the modelview matrix, used for transforming the geometry you draw, and specifying the camera  
	- the projection matrix, used for controlling the way the camera image is projected onto the screen (see later)  
- This is what you saw in the vertexShader.  
	- If you don’t write a vertexShader, it happens automatically.  
	- P drawn = ProjectionMatrix x ModelviewMatrix x P specifed
 