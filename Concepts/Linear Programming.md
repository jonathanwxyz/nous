#Algorithms-and-Data-Structures 

### What is it?
- ==An optimisation problem==
- We want to minimise or maximise something, this thing trying to be optimised is called the ==object function==
- Given a set of constraints

### The Requirements
- Our requirements can be expressed as linear relationships  
![[Pasted image 20230407132435.png]]
- The constraints are inequalities:  
$$\leq$$
- All the variables must be greater or equal to zero
- This format is called ==standard form==
	- There are examples of converting to standard form [[Linear Programming Standard Form Examples|here.]]

for example:
![[Pasted image 20230407132505.png]]
![[Pasted image 20230407132517.png]]

### Visualising Linear Programming Problems
For the problem outlined above we might have parameters for the variables (other than the ones we're trying to optimise). i.e.
![[Pasted image 20230407133819.png]]
so we now have the problem:
- Maximise:  
5xb + 4xw  
- Constrained by:  
xb + xw ≤ 4  
2xb + 10xw ≤ 30  
10xb + 2xw ≤ 30  
- And:  
xb, xw ≥ 0

We can draw this out on a graph, colouring in the invalid regions:
![[Pasted image 20230407133926.png]]
We're left with an area in the middle that satisfies the constraints

To optimise this we draw a line an move it till we find the best outcome
![[Pasted image 20230407134047.png]]
The best outcome is always at the intersection of multiple constraints
### Matrix Form
![[Pasted image 20230407140043.png]]