### Questions
##### 1. Canny has two thresholds that control the edge thresholding process. What is their purpose?
This diagram illustrates the purpose of the two thresholds well:
![[Pasted image 20230425152212.png]]
Above maxVal (the higher threshold), we are sure that the edge in question is really and edge as it has a very high intensity gradient. Under minVal (the lower threshold), we deem the edge in question to not be a valid edge as the intensity gradient is too low. In between the two thresholds we're looking for an edge in question to be connected to an edge with an intensity gradient above maxVal. So A would be deemed an edge, C would be deemed an edge, but B would not.

##### 2. What is the purpose of the aperture parameter? What is the result of changing it from 3 to 5, 7, 9 or greater?
The aperture parameter alters how intricate or complex the edges can be in order to count as an edge. For example, a low aperture like 3 might only detect edges that are quite gradual (such as a horizon). Whereas a high aperture might detect very sudden contours (such as the outline of a cloud). So the higher the aperture is, the more granular edges one would expect to see.

##### 3. The Hough transform has two parameters that specify the resolution of the accumulator. Their default values are 1 and π/180. What is the effect of increasing the first and reducing the second?
The effect of increasing the first and reducing the second parameter mentioned is that the edges become more segmented.

The result of increasing the first parameter - the distance resolution of the accumulator rho - increases the number of rows in the accumulator matrix. The effect on the transformation is that there will be fewer lines being drawn, because the higher resolution leads to fewer overlapping points when filling the accumulator, thus the lines become more segmented.

Decreasing the second parameter - the angle resolution of the accumulator theta - increases the number of columns in the accumulator matrix. The effect on the transformation is that there are more calculations, and more lines found.

##### 4. The Hough transform has a pair of parameters that determine the minimum length of a line that can be accepted, and the maximum gap between two segments if they are to be considered part of the same line. What is the effect of changing these values?
Changing the minimum length of a line that can be accepted is quite self explanatory. If the value is increased, fewer lines will be rendered as shorter lines might be under the minimum length and thus discarded.

Changing the maximum gap between two points changes which lines are allowed to be drawn between points. When the value is low, there will only be lines drawn between points that are close to one another. When the value is high, lines may be drawn between points which are far from one another.

##### 5. How close are the computed horizons to where you think the horizon should be? What might cause any discrepancy?
The computed horizons are often a little bit above where I might expect them to be, particularly on the images from space. This discrepancy might be due to the gradient of the atmosphere into space, when this gradient is converted to grayscale even the thinner bits of the atmosphere might be lightened up in comparison to space which stays black. Also the intensity gradient within the atmosphere probably isn't that high as it is a gradient.