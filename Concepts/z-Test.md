#Machine-Learning 

### Algorithm
Steps:
1. Compute a quantity $z_p$ as below:
	- ![[Pasted image 20230216153023.png]]
2. Look up the table below to get the confidence value p.
	- ![[Pasted image 20230216153050.png]]
3. Compute the final probability by
	- ![[Pasted image 20230216153112.png]]

### Comments
- It only compares two hypotheses at a time.  
- [[ML Hypothesis|Hypotheses]] can be tested on different sets of samples.  
- The approximation works well for test sets containing over 30 samples.