#Visual-Computing 

There are 3 main shading methods:
1. [[Flat Shading]] aka constant
2. [[Gouraud Shading]] aka intensity
3. [[Phong Shading]] aka normal-vector
![[Pasted image 20230404141320.png]]

### Rendering Expense
- Roughly, our local illumination model takes about 60 floating-point operations to compute a colour for a pixel  
- For a Gouraud-shaded triangle, that’s 180 flops, then about 2 per pixel  
- For a Phong-shaded triangle, that’s 60 flops for every pixel