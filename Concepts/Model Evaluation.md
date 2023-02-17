#Machine-Learning 

[[Sample Error and True Error|True error]] of a model A: Expectation of the true error of the [[ml hypothesis|hypothesis]] A(T) with randomly drawn training set T.

![[Pasted image 20230216145257.png]]
errorD:
Hypothesis evaluation:  
- Train your model using training data T.  
- Estimate the true error using a new test data E.

ETD:
Model evaluation:  
• Approximate the expectation, by running multiple training- testing trials and average the test error rates.

This multiple training idea motivates the evaluation methods like [[Random Subsampling]], [[Leave One Out (LOO)]], [[Bootstrap Sampling]], [[K-fold Cross Validation]]

With multiple models we need to do [[Model Comparison]]