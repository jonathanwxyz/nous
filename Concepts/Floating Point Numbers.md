This is a way of representing numbers with decimal points in computers efficiently.
We must trade off range for accuracy.

### IEEE754 (32 bit - single precision)
Here we decide in advance how the bits will be interpreted:
![[Pasted image 20221227150659.png]]
- **Sign** bit: 0 - positive, 1 - negative ^b24e41
- **Exponent**: range of the number as a power of 2 ^3702b8
- **Mantissa**: 1.\<mantissa\> as an unsigned value ^5d9f91

There are many special cases but above contains the spirit of it
![[Pasted image 20221227151036.png]] ^509e62
#### Useful Resources
- https://youtu.be/tx-M_rqhuUA
- https://youtu.be/4DfXdJdaNYs


### Normalised Floating Point Form
- DISTINCT FROM IEEE 754 format!
- Provides a unique representation of a number
- allows the maximum possible precision for a given number of bits
- Normalised version of a positive number always starts with 0 point 1
	- negative: 1 point 0
- If you had a Mantissa of 8 bits, the normalised version would allow for 7 of the 8 bits to be used after the binary point
- Example:
![[Pasted image 20221227183638.png]]
![[Pasted image 20221227183701.png]]
- Another example
![[Pasted image 20221227185304.png]]

### bfloat16

^d049d7

![[Pasted image 20221231144750.png]]
- Used by Google in their [[Google TPU|TPU]]
- The dynamic range of bfloat16 is greater than that of fp16. (& identical to that of fp32)
- Trading of precision for range

### Microsoft Floating Point
![[Pasted image 20221231145300.png]]
- Uses a ==shared exponent== to achieve the dynamic range of floating-point formats such as fp32 and bfloat16 while keeping storage and computation costs close to those of integer formats.  
- Through the co-evolution of hardware design and algorithms, MSFP16 achieves 3x lower cost compared to Bfloat16, and MSFP12 achieves 4x lower cost compared to industry standard INT8 while delivering a comparable or better accuracy.


