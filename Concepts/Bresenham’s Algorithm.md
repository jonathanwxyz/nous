#Visual-Computing 

- y = mx + c  
- As we move horizontally x changes by 1 pixel  
- So $y_{n+1} = y_n + m$  
- Round $y_{n+1}$ to the nearest pixel

![[Pasted image 20230216171603.png]]

- Need to swap x and y according to gradient of the line  
- Bresenham (1965) developed a fast algorithm using only integer arithmetic  
- Still in use today