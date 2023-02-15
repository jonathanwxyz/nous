#Machine-Learning 

- Bootstrap is based on sampling with replacement.  
- Repeat the following process K times:  
	- Randomly select (with replacement) M samples and use these for training.  
	- The remaining samples that were not selected are for testing. The number of testing samples can change over repeats.  
	 - ![[Pasted image 20230215230151.png]]
- The final error estimate is computed by
	- ![[Pasted image 20230215230207.png]]
	- Average of the errors

### Related
[[Holdout Method]]
[[Random Subsampling]]
[[K-fold Cross Validation]]
[[Leave One Out (LOO)]]