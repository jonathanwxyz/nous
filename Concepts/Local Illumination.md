#Visual-Computing 

### Approximation
In order to model local illumination, that is the way that light bounces off of objects we must use approximations.
The more sophisticated the approximation, the longer the render time is.

### Step by step model
- start with light intensity only (no colour)  
- ambient illumination  
- [[What are Diffuse and Specular Reflection?|Diffuse Reflection]]  
- a positional light source  
- [[What are Diffuse and Specular Reflection?|Specular Reflection]]  
- coloured lights and surfaces

### Different Types of Illumination
1. ambient illumination  
2. point illumination source at infinity (directional illumination)  
3. point illumination source in the scene

### Ambient Illumination
- The amount of ambient light diffusely reflected from a surface is:
$$I_{ambient} = k_aI_a$$
- Where $k_a$ is the ambient reflection coefficient of the surface and is between 0 and 1 inclusive
- $I_a$ is the monochrome intensity of ambient light
![[Pasted image 20230304203543.png]]
Using this method alone we have no real concept of depth or shadow.

#### What's lacking?
- We need to model the effects of:
	- different angles of incidence  
	- different distances from the light source

### Directional Lighting
![[Pasted image 20230304203645.png]]

![[Pasted image 20230304211912.png]]
We're considering the light as being an infinite distance away

==Lambert's law==
- Light source of intensity $I_p$
- Effective intensity $I_e$ received is
- $$I_e = I_p {cos}\theta$$
Now let's consider light with intensity $I$ with a cross section $x$:
![[Pasted image 20230304212201.png]]

![[Pasted image 20230304212346.png]]
At an angle the light is less intense as it's split over a greater area

### Diffuse Reflectivity
- We describe the diffuse reflectivity of a surface by assigning it a value $k_d$, the ==diffuse reflection coefficient== of the surface (0 to 1 inclusive)
- ![[Pasted image 20230304212640.png]]
- Remember for normalised vectors, their [[Dot Product (Inner Product)]] is the cosine between them

So for a model-so-far we have
![[Pasted image 20230304212801.png]]
the ambient component is from the [[#Ambient Illumination|previous section]].
![[Pasted image 20230304212831.png]]
It's better. next we'll at a distance from light

### Light Source Distance
- Physically, light intensity falls off with the square of distance travelled:
	- ![[Pasted image 20230304212958.png]]
- In computer graphics this equation does't really work as we only have a limited number of pixel intensities and the d^2 term changes too rapidly so instead we use an approximation:
- ![[Pasted image 20230304224359.png]]

So our model-so-far is
![[Pasted image 20230304224426.png]]
This build upon the [[#Diffuse Reflectivity|previous section]].


### Specular Reflectivity
![[Pasted image 20230306125504.png]]
We want to find out how much light will be at $\hat{V}$ at an angle of $\phi$ from $\hat{R}$ (The reflection of $\hat{L}$)
![[Pasted image 20230306125708.png]]
We're looking for a function $$I_{specular} = S(\phi,\theta,\lambda)$$
$\lambda$ is the wavelength of the light.

When V coincides with R, the observed specular will be 100%.
As the angle between increases, observed specular decreases
A decent approximation for this relationship is $$F = cos^n\phi$$
![[Pasted image 20230306130255.png]]
This is called ==Phong's specular function==
Using vectors we can rewrite this as $$I_{specular} = I_p(\hat{R}.\hat{V})^n$$
Where n is normally between 1 and 200 inclusive.

So we've accounted for $\phi$ but we still need to consider other factors.

We need to account for how reflective a material is at different angles and with different wavelengths of light.
![[Pasted image 20230306130551.png]]
![[Pasted image 20230306130627.png]]

A good equation to model this is ==Fresnel's equation== ==NO NEED TO MEMORISE==
![[Pasted image 20230306130733.png]]
But this is complicated and slow compared to more approximate alternatives.
![[Pasted image 20230306130809.png]]

In practice we use a single constant for a surface called $k_s$, the ==specular reflection coefficient==, between 0 and 1 inclusive.
![[Pasted image 20230306131050.png]]

Here's our model-so-far building on the [[#Light Source Distance|previous section]]:
![[Pasted image 20230306131126.png]]
![[Pasted image 20230306131138.png]]


### Coloured Lights, Surfaces, Multiple lights
So far we've only considered light intensity, not colour.
To express colour we just need to work out I (intensity) for each colour
![[Pasted image 20230306131314.png]]
![[Pasted image 20230306131325.png]]
So we need to do this for Blue and Green above.


For multiple lights we simply work out each light separately and sum
![[Pasted image 20230306131413.png]]
![[Pasted image 20230306131428.png]]