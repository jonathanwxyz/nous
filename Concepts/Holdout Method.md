#Machine-Learning 

- Holdout method: Split up your dataset into a training and test set.  
	- Train your model using the training set.  
	- Estimate your model error using the test set.
![[Pasted image 20230215224859.png]]

### Drawbacks
- If the dataset is small, we may not be able to set aside a portion of the dataset for testing.  
- The holdout estimate of error rate can be misleading if we happen to get an “unfortunate” split (sample error true error).

### Related
[[Random Subsampling]]
[[K-fold Cross Validation]]
[[Leave One Out (LOO)]]
[[Bootstrap Sampling]]
