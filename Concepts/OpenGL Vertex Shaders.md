- All shapes are made of vertices  
- Vertex shader receives each in turn  
- Does some processing  
- sets a values for gl_position (a vec4), which is where this vertex will appear onscreen  
- The information eventually reaches the Fragment Shader for this vertex
![[Pasted image 20230214150605.png]]

### Simplest vertex shader
```c
// projection and modelView are provided by three.js  
void main ()  
{  
	gl_Position = projectionMatrix *  
	modelViewMatrix *  
	vec4(position, 1.0);  
}
```
three.js also adds light data, vertex colours, vertex normals etc.

