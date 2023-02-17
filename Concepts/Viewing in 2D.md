#Visual-Computing 

![[Pasted image 20230217173352.png]]
We find the matrix $M_{\text{view}}$ which transforms the window to the viewport.
$M_{\text{view}}$ is called the ==viewing transformation==.

### Finding $M_{\text{view}}$
M1 : Translate by (-x0, -y0) to place the window at the origin  
M2 : Scale the window to be the same shape as the viewport  
M3 : Shift to the viewport position

- M1 : Translate (-x0, -y0)  
- M2 : Scale (u1-u0/x1-x0, v1-v0/y1-y0)  
- M3 : Translate (u0, v0)  
- M_view = M3 * M2 * M1
![[Pasted image 20230217173736.png]]
![[Pasted image 20230217173759.png]]

### Clipping
We may want to remove those parts of primitives whose coordinates are outside the window.
There are standard algorithms for clipping
![[Pasted image 20230217173828.png]]

### Multiple Windows and Viewports
![[Pasted image 20230217173951.png]]
Notice how V2 has been magnified