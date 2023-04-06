#Algorithms-and-Data-Structures 

### What is it?
![[Pasted image 20230403120549.png]]
![[Pasted image 20230403120558.png]]
A Minimum Spanning Tree (MST) will connect all nodes with with the sum weight of the edges minimised.

#### Formally:
![[Pasted image 20230403120658.png]]

### Generic Greedy Algorithm for creating a MST
- Grow the MST one edge at a time
- Not always globally optimal
![[Pasted image 20230403120803.png]]

#### Correctness through loop invariant method
![[Pasted image 20230403120854.png]]

### Cuts and Light Edges
![[Pasted image 20230403121051.png]]
![[Pasted image 20230403121106.png]]

### Safe Edges
![[Pasted image 20230403121128.png]]



### Different Algorithms
- [[Kruskals Algorithm]]
- [[Prim's Algorithm]]