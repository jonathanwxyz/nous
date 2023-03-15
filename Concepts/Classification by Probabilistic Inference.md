#Machine-Learning 

A form of [[Classification]] where we model the probability that an input corresponds to a certain class.

- Model the ==posterior class probability== p(class k|x)
- Find the most likely class: ![[Pasted image 20230307114441.png]]
![[Pasted image 20230307114458.png]]

### How can we model the posterior class probability?
- We can directly construct the posterior function
	- [[Logistic Regression]] belongs to this approach
	- In [[COMP24112 - Machine Learning]] this is referred to as approach II
- We can construct the likelihood and prior functions, then compute the posterior function following [[Bayes Theorem]].
	- Naive Bayes classifier belongs to this approach
	- In [[COMP24112 - Machine Learning]] this is referred to as approach III
		 - Approach I refers to [[Discriminant Function by Thresholding]]
- ![[Pasted image 20230307114736.png]]
![[Pasted image 20230307115150.png]]

### Comparison to Deterministic Model
![[Pasted image 20230307115202.png]]
This probabilistic approach returns an output with quantified uncertainty
![[Pasted image 20230307115505.png]]
Whereas a deterministic model such as [[Discriminant Function by Thresholding]] just returns a particular output

### Binary and Multiclass classification
Use the logistic sigmoid (binary classification) or softmax function (multi-class classification) to compute the class posterior from a linear model
![[Pasted image 20230307134318.png]]
![[Pasted image 20230307134405.png]]
![[Pasted image 20230307134414.png]]
![[Pasted image 20230307134432.png]]
![[Pasted image 20230307134444.png]]

![[Pasted image 20230307142028.png]]
