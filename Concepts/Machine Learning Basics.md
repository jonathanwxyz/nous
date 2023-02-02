#Machine-Learning 

### What can Machine Learning Do?
- Automate a process
- Automate decision making
- Extract knowledge from data
- Predict future events

Machine Learning is about writing code to ==make the computer learn from data==.
It's often used for Artificial Intelligence and Data Science tasks.

- What might we want to do with the data?
	- ==Prediction==: What can we predict about this phenomenon?
	- ==Description==: How can we describe/understand this phenomenon in a new way?

### History
See [[Artificial Intelligence History]]

### Machine Learning Strategy
- **Data + Model** Strategy
	- ![[Pasted image 20230131122133.png]]
	- **Data X**: collection of experience E.
	- **Function f**: Function output provides answers/solutions to Task T.  
	- **Parameters θ**: control model behaviour.  
	- **Objective function O(θ)**: It computes a performance P of task T.  
	- **Optimisation min O(θ)**: learning (or training).

#### Optimisation
Mathematical Optimisation systematically finds the inputs that compute the best outputs
![[Pasted image 20230131123028.png]]
![[Pasted image 20230131123056.png]]

### Machine Learning Pipeline
#### Model Construction
- To prepare experience (E) in proper ==data== format.  
- To characterise a task (T) by a ==parametric model==.  
- To characterise a performance metric (P) by an ==objective function==.
#### Training
- To determine the model through ==optimising== the objective function.
#### Evaluation
- To assess the determined model using a performance metric.
### Machine Learning Ingredients
- ==Data== (Experience)  
- ==Model==: A piece of code (model function) with some parameters that need to be optimised.  
- ==Loss function==: The function you use to judge how well the parameters of the model are set. It is also called error function, cost function, objective function.  
- ==Training algorithm==: The algorithm that optimises the model parameters, using the error function to judge how well a model is performing.
Finally, the model with determined parameters is the thing you have to package up and send to a customer.
