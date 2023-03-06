#Visual-Computing 

We can think of viewing a model in computer graphics similar to how one uses a [[3D Graphics Camera|camera]] to view the real world:
![[Pasted image 20230217144325.png]]

The pipeline from a vertex to a pixel can be mapped:
![[Pasted image 20230217144418.png]]

The [[3D Viewing Default View]] can be seen here.

[[3D Projections]] are discussed here.

### Summary
We can now summarise the steps of the viewing process  
1. The modelling transformation arranges objects in our 3D world  
2. The viewing transformation transforms the world to give the same view as if it were being photographed by a camera  
3. The projection transformation performs a parallel/perspective projection within limits (the clip planes)  
4. Those parts of the 3D world outside the clip planes are discarded  
5. If it’s a perspective view, the perspective division “flattens” the image  
6. The viewport transformation maps the final image to a position in part of the display screen window.