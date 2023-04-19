A standard is required so that all parties know the exact colour being specified

### CIE 1931 XYZ colour space
![[Pasted image 20230417120953.png]]
![[Pasted image 20230417121014.png]]
![[Pasted image 20230417121449.png]]

### YCrCb
Used for broadcasting, good for when there were both black and white and colour tvs.
![[Pasted image 20230417121152.png]]
Conversion from RGB:  
Y = 0.299 R + 0.587 G + 0.114 B  
Cb = -0.1687 R - 0.3313 G + 0.5 B + 128  
Cr = 0.5 R - 0.4187G - 0.0813 B + 128

Less detail in Cb and Cr so fewer pixels stored:  
One Cb and one Cr pixel per four Y pixels

### Perceptual Spaces
- Equal distances on CIE diagram DO NOT correspond to equal changes in perceived colour  
- This is important for measurement and to allow colours to be described in a way suitable for humans

#### IHS
- Intensity  
	- Aka Brightness  
	- Weighted average of RGB  
- Hue  
	- The basic colour  
	- An angle from 0 to 359  
- Saturation  
	- Depth of colour  
	- (Lower saturation means more diluted with white)
![[Pasted image 20230417121637.png]]
![[Pasted image 20230417121652.png]]

#### Lab Colour Space
- Also known as L*a*b* and CIELAB  
	- Used in Photoshop  
- Device independent  
- L* represents lightness  
	- 0 = black, 100 = white  
- a* represents green to red  
	- -a is green, +a is red  
- b* represents blue to yellow  
	- -b is blue, +b is yellow
![[Pasted image 20230417121743.png]]

#### Segmentation with HSV
Colour image converted to HSV (hue, saturation, value) channels
![[Pasted image 20230417123706.png]]

![[Pasted image 20230417123716.png]]

![[Pasted image 20230417123729.png]]


### Colour to Greyscale
![[Pasted image 20230417123331.png]]
By just averaging out the colours we get the same value for each of the colours. This works, but it isn't how humans perceive colour, we tend to see the green as being brighter. So different programs use different linear combinations (weightings) of channels.

