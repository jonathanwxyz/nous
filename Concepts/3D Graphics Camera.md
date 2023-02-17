#Visual-Computing 

In 3D graphics, the idea of a camera is only really an analogy. ==We simulate a
camera by transforming the model==.

The camera analogy is mapped out with the information:
![[Pasted image 20230217145516.png]]
- The camera is located in position **E** is the ==Eye point==,  and is looking towards **C** which is the ==Centre of interest==. 
- Additionally there is **V** which is the ==view up vector==, the up direction of the camera.
- There's also $\hat{S}$, $\hat{U}$ and $\hat{F}$ hat which are fixed, these are used as the coordinate system of the camera.
	- E, C and V are used to derive these

By default in [[OpenGL]], the [[3D Viewing Default View]] is at (0,0,0) looking down the z-axis.
We move the camera from the default to the desired position and orientation through the transformation $T_c$.
As there isn't really a camera the actual transformation we apply is the inverse:  $T_c^{-1}$ 
![[Pasted image 20230217165400.png]]
We can see here we can move the world around the camera to the same effect as moving the camera to the world.

### Defining the Camera Coordinates
Easiest is $\hat{F}$:
1. F = E - C
2. Normalise F to length 1 and call it $\hat{F}$
![[Pasted image 20230217160657.png]]

Next we must consider the up direction (V) of the camera, here are some examples:
![[Pasted image 20230217160828.png]]

Work out $\hat{S}$ with [[Cross Product (Outer Product)]]:
$$\hat{S} = \text{normalise}(\hat{F} \times \hat{V})$$

Work out $\hat{U}$:
$$\hat{U} = \text{normalise}(\hat{S} \times \hat{F})$$

F is orthogonal to U and S.

### Deriving $T_c^{-1}$
1. translate the origin of the camera system to (0,0,0):
 ![[Pasted image 20230217164016.png]]
2. now rotate the camera axes to be coincident with the world axes, with $\hat{F}$ aligned with –Z
![[Pasted image 20230217164136.png]]
3. $T_c^{-1} = T2 * T1$

![[Pasted image 20230217164228.png]]
