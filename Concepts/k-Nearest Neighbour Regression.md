#Machine-Learning 

Similar to [[k-Nearest Neighbour Classification]] however the output is in the format of [[Regression]] (continuous numbers).

### k-NN Regression Rule
- Given a set of training samples {features, output}
- Each sample corresponds to a data point in the feature space
algorithm:
- We pick a testing point
- For each training datum, measure the distance to the testing point
- Sort these distances
- Select the k nearest points
- calculate the average of these points (this is the output)