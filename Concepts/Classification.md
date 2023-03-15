#Machine-Learning

### What is it?
A form of [[Supervised Learning]] which maps inputs to classes/discrete outputs
- Goal: Identify which categories a data pattern belongs to.  
- Training data: Observed data patterns and their ==category memberships==.

#### Formally
![[Pasted image 20230215210742.png]]
We have Samples which are comprised of features and class label. We have a feature vector and a set of all of the class labels

### Different Types of Classification
- ==Binary classification==: classify into one of the two classes.  
- ==Multi-class classification==: classify into one of the many classes.  
- ==Multi-label classification==: classify into some of the many classes
	- There is no constraint on how many classes a sample can belong to.  
	- For example document classification might label documents with many different topics
- ==Structured classification==: classify into structured classes
	- Classes can be organised in sequence, tree, lattices, graph.
	- ![[Pasted image 20230131134214.png]]

### Performance Measures

^f01908

- [[Classification Accuracy and Error]]
- [[Confusion Matrix]]
- [[Precision (in Confusion Matrix)]], [[Recall (in Confusion Matrix)]], [[F1 Score]], [[Specificity (in Confusion Matrix)]]

### Methods For Classification
There are 3 approaches outlined in [[COMP24112 - Machine Learning]] seen in:
- [[Discriminant Function by Thresholding]]
- [[Classification by Probabilistic Inference]]

### Notation for multi-output
![[Pasted image 20230307124334.png]]
![[Pasted image 20230307132444.png]]

