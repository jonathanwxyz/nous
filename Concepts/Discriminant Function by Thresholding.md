#Machine-Learning 

This is a form of [[Classification]] where we map an input to a class. For instance:
![[Pasted image 20230307112912.png]]

### Binary Classification
Here we focus on ==Binary Classification==
- Step1: Construct a real-valued function f(x).  
- Step2: Convert the output to a class prediction by thresholding.
![[Pasted image 20230307113017.png]]
- The real number t can be treated as a [[hyper-parameter]]
- A common setting is t = 0
- ![[Pasted image 20230307113249.png]]
- In the example above, inside the green line corresponds to Class A and outside is Class B
- The set of input variables that give f(x) = t is called a level set of f.
- In [[COMP24112 - Machine Learning]] this is referred to as approach I, approach II and III can be found in [[Classification by Probabilistic Inference]]
![[Pasted image 20230307115135.png]]

### Multiclass Classification
Construct a multi-output linear model, then construct the discriminant function for each class.
![[Pasted image 20230307134057.png]]