#Machine-Learning 

- Take [[regression]] as an example.  
- Expected squared error for a new test sample:
	- ![[Pasted image 20230215232218.png]]
- With some calculation, it has
	- ![[Pasted image 20230215232259.png]]
- ![[Pasted image 20230215232312.png]]
![[Pasted image 20230215231921.png]]
- Bias error:  
	- ![[Pasted image 20230215232106.png]]
	- Bias error measures how much the averaged prediction is close to the true value.
- Variance error:  
	- ![[Pasted image 20230215232122.png]]
	- Variance error measures how much the prediction varies among different realisations of the model.
- Over-fitting: low bias error, high variance error, e.g., an over complex model that is sensitive to small fluctuations in the training set.  
- Under-fitting: high bias error, low variance error, e.g., an excessively simple model.