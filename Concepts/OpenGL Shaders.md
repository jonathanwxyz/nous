#Visual-Computing 

Recall that in [[OpenGL]] there is a [[Programmable Graphics System Pipeline]]

There are different shaders:
[[OpenGL Vertex Shaders]]
[[OpenGL Fragment Shaders]]

Inbetween the shaders we have:
![[Pasted image 20230214150933.png]]

### How do the shaders get the data?
Different strategies:
![[Pasted image 20230214151353.png]]

#### Uniforms
- Sent to vertex and fragment shaders
- They stay constant throughout the frame
- Usually single values  
	- e.g. light positions, material colour, shininess ...

#### Attributes
- Values applied to individual vertices. Only available to the vertex shader  
- Could have an array of attributes:  
	- One per vertex

#### Varyings
- Variables declared in the vertexShader that are shared with the fragment shader  
- So a way of passing data from vertexShader to fragmentShader
- Must declare a varying variable of the same name and type in both shaders

