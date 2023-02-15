- Determines what colour a pixel is given
- How to colour an object that has vertices?  
- Fragment shader must set a value for gl_FragColor (a vec4) which is the final colour of the fragment
![[Pasted image 20230214151022.png]]

### Simplest fragment shader
```c
void main ()  
{  
gl_FragColor = vec4(1.0, 0.0, 1.0, 1.0);  
// RGBa  
}
```
The shaders need to be attached to the mesh
