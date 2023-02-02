#Visual-Computing 

### What is it?
- Open Graphics Library; started in 1992. It's a platform independent standard for [[Portability|portable]] graphics programming.
- Operated by Khronos which has over 100 companies running it.
- ![[Pasted image 20230201141313.png]]
- Separates the concerns of the software and hardware.
- OpenGL is a ==specification== for an Application Programmer's Interface (API)
	- So defines a set of functions for doing 3D graphics
- Used in mobile games, research, CAD, everywhere
- The main features of OpenGL  
	- 3D graphics (points, lines, polygons...)  
	- coordinate transformations  
	- a camera for viewing  
	- hidden surface removal  
	- lighting and shading  
	- texturing  
	- pixel (image) operations

### Pipeline
- In previous versions of OpenGL (pre 3.0) there was a fixed pipeline which might look similar to [[Basic Graphics System Architecture]]
- Post 3.0 there is a [[Programmable Graphics System Pipeline]]
- Compare Fixed vs Programmable [[Fixed vs Programmable Pipeline|here]]

### GLUT
GL Utility Toolkit
- OpenGL only generates pixels, for interaction (mouse, keyboard, etc.) we could use the GLUT library
- Simple menu systems
- Primitives
	- Sphere, torus, cone, cube  
	- \[tetra|octo|dodeca|icosa\]hedron  
	- teapot

### GLU
GL Utility Library
- provides functions which “wrap up” lower-level OpenGL graphics  
	- Curves, surfaces, cylinder, disc, quadrics...  
- Utility functions  
	- Viewing  
	- Textures  
	- Tessellation