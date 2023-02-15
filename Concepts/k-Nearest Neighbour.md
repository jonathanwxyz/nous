### Content
- [[History of k-Nearest Neighbour]]
- [[k-Nearest Neighbour Classification]]
- [[k-Nearest Neighbour Regression]]
- [[Instance Based Learning]]

### Things to consider
#### Distance Calculation
Most common way is ==Euclidean Distance==
![[Pasted image 20230214115719.png]]
(basically generalised pythagoras' theorem)

A more generalised way to calculate distance is ==Minkowski Distance==
![[Pasted image 20230214115900.png]]
Where if t=2 we get euclidean distance
if t=1 we get ==Manhattan (city block) distance==

An alternative is to use a ==Similarity Measure==
![[Pasted image 20230214120426.png]]
![[Pasted image 20230214120458.png]]
Similarity of 1 means they're identical
We can also convert a similarity to a distance using:
![[Pasted image 20230214120604.png]]

#### Effect of neighbour number k
- Hyper-parameter: [[k-NN Neighbour Number k]]
- Small k: We may model noise!  
- Large k: Neighbours will include too many samples from other classes, which can negatively affect the prediction.

#### Effect of training samples
- Small number of training samples:  
	- insufficient information  
- Large number of training samples:  
	- more information  
	- but, time and memory cost consuming (distance calculation, sorting)  
- Noisy training samples:  
	- inaccurate prediction
#### Fast neighbour search
- Study fast computation of nearest neighbours is an active research area in [[machine learning]].  
- Naïve Approach: brute-force compute distances between all pairs of samples and sort.  
- Tree-based methods:  
	- Basic idea: Knowing A is very distant from B, and B is very close to C, it is certain that A and C are very distant, without having to explicitly calculate their distance. Apply this to reduce the number of distance calculations.  
	- Variaties: K-D tree, Ball tree, etc.
 
#### Summary
- k-NN is the simplest machine learning algorithm.  
- It can be used for both classification and regression.  
- No explicit training.  
	- A non-parametric method: no parameter to be optimised  
- The algorithm relies on a distance measure.  
- More training data provides more information to learn, but results in high memory cost (needs to store all the training data).  
- The neighbour number k is a hyper-parameter to be selected by the user.  
	- Too small: sensitive to noise  
	- Too large: inaccurate prediction
