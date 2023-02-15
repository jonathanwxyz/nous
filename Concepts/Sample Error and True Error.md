- ==Hypothesis==: Prediction made by a trained machine learning model.  
- ==Sample error== of a hypothesis (error S ):  
	- Error computed by a performance metric using a set of data samples. 
	- Error in what the model outputs relative to our sample
- ==True error== of a hypothesis (error D ):
	- For [[classification]], it is the ==probability that a single sample is misclassified==, where the sample is randomly drawn from a distribution.
	- For [[regression]] case, it is the ==expectation of the error==. See example:
		- ![[Pasted image 20230215223451.png]]
	  - Error in the what the model outputs relative to the objective truth of reality

- What we wish to know is the true error, however this is seldom possible.
- We CAN always compute the sample error (simply the error in our sample)
- Infinite samples: sample error converges to true error
- Insufficient samples: Sample error may not approximate true error well.