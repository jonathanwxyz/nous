#Visual-Computing 

A way of representing scenes in computer graphics by having a list of individual [[OpenGL Polygons|polygons]], and colouring them separately

### Problems
- Huge waste of storage space
	- Most models share surfaces, not individual polygons, so we could share vertices rather than have ==many copies of the same vertices==
- Loss of semantics (does a polygon belong to a cow?)
- Interaction with the model is difficult
![[Pasted image 20230216165019.png]]

### Alternatives
[[Polygon Meshes]]