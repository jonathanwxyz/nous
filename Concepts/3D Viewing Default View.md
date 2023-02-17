#Visual-Computing 

![[Pasted image 20230217144622.png]]
The projection is orthogonal, with projectors parallel to the z axis.
[[OpenGL]] projects the user’s lines (red) onto the z=0 plane (blue)

The z=0 plane then gets mapped to the display screen, and whatever geometry is there gets scan-converted (aka rasterised) and the z-buffer applied.
![[Pasted image 20230217144905.png]]

