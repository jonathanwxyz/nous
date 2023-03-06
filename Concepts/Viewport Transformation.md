▪ After perspective division, we now have 3D coordinates  
▪ OpenGL has scaled these into the range \[-1,+1\] in X, Y and Z  
▪ In the final step, using only the X and Y values, OpenGL computes a transformation from \[-1,+1\] to the display screen  
▪ Either the whole window  
▪ Or a part of it called a viewport  
▪ But we retain Z, to remove hidden surfaces