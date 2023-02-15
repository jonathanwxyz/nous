#Machine-Learning 

- Divide the entire dataset into K partitions.  
	- For each of the K experiments, use (K-1) partitions for training and the remaining one for estimating the error rate E i.  
	 - ![[Pasted image 20230215225435.png]]
- The final error estimate is computed by
	- ![[Pasted image 20230215225453.png]]
	- Averaging out the errors
- Advantage: all the examples in the dataset are eventually used for both training and testing.

### Comments
- Each sample is used as the testing samples only once, but as the training samples K-1 times.  
- All the test sets are independent, but there is overlapping between training sets.  
- Low number of K results in insufficient training-testing trials.  
- High number of K results in small testing set potentially with high variance.  
- Some standard settings: 10-fold CV, 5-fold CV.

### Related
[[Holdout Method]]
[[Random Subsampling]]
[[Leave One Out (LOO)]]
[[Bootstrap Sampling]]