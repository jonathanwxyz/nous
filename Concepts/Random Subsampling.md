#Machine-Learning 

- Perform K data splits of the entire dataset.  
	- Each split randomly selects a fixed number of samples for testing, and uses the remaining samples for training.  
	- For each data split, the classifier is trained from scratch using the training samples, and its error rate is estimated with the testing samples (denoted by E i for the i-th split).
		- ![[Pasted image 20230215225306.png]]
	- The final error estimate is computed by 
		- ![[Pasted image 20230215225217.png]]
		- Essentially averaging out the errors

### Related
[[Holdout Method]]
[[K-fold Cross Validation]]
[[Leave One Out (LOO)]]
[[Bootstrap Sampling]]