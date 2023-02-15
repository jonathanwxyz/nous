#Machine-Learning 

### What is it?
A primitive way of measuring how good a [[Classification]] [[Machine Learning]] model is. Here are the equations:
$$\text{Classification accuracy} = \frac{\text{number of correctly classified samples}}{\text{total sample number}}$$
$$\text{Classification error} = \frac{\text{number of wrongly classified samples}}{\text{total sample number}}$$

### Disadvantages
1. Unreliable for assessing ==unbalanced== data
	- e.g. 95 samples in A and 5 samples in B. If the model says they're all A then we have 95% accuracy despite it being a BAD classifier
2. Doesn't give much information about how classifiers behave
	- e.g![[Pasted image 20230215211905.png]]
		- c1 is better at classifying Bs more accurately and c2 is better at classifying As despite both of them having the same overall accuracy
		- So both models behave quite differently

