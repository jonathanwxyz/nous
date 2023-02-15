Given limited data we will probably encounter these issues:
- ==Bias== issues
	- Accuracy of the ==training== samples can be a ==poor== estimator of the accuracy of ==unseen== samples.
	- Can be an ==optimistically biased== estimate of the hypothesis over future unseen data
	- To deal with the bias issue, it is better to choose ==a new set of test examples independent of the training examples==.
- Variance Issue:  
	- Accuracy of a new set of test samples can ==still vary from the true accuracy==, depending on the makeup of a particular set of test samples.  
	- Smaller set of test samples can result in higher variance.
 