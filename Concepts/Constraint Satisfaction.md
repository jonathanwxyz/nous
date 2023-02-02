# Constraint Satisfaction Problems
### Example: Timetabling 
Needing to assign timetables for students is a CSP. We may have both hard and soft constraints:
![[Pasted image 20221015182043.png]]

## Definitions
![[Pasted image 20221015182530.png]]
![[Pasted image 20221015182601.png]]
![[Pasted image 20221015182611.png]]
Arity is number of arguments in that relation
![[Pasted image 20221015182843.png]]

![[Pasted image 20221015222157.png]]

### Example of these definitions
![[Pasted image 20221015222745.png]]

### Another Example, colouring graphs
![[Pasted image 20221015223007.png]]
In plain english: we colour in nodes (vertices) in k colours and adjacent vertices can't be the same colour
![[Pasted image 20221015231438.png]]
In the above case, k = 3 so we say the domain each vertex can be is in 1,2 or 3.
Rij enumerates all of the possible legal combinations for 2 vertices


## CSPs can be viewed as search problems
![[Pasted image 20221015231931.png]]
The constraints might mean we don't need draw out a full tree. For instance a constraint where x1 = b1 and x2 = b6 cannot exist, we have the tree:
![[Pasted image 20221015232105.png]]
If we do search on the tree (depth first search is best I think) we know we have found a solution to the problem if we get to a depth of $n$ where $n$ is the number of variables. All combinations that are drawn out on the tree are valid, those that aren't shouldn't be in the tree. So if a node has no daughters and it isn't at depth $n$ we must backtrack

This solution isn't practical for large values of $n$ as the complexity explodes.

# Constraint Propagation
Also known as Forward Checking

![[Pasted image 20221015233000.png]]
- $R_{j,i}$ - All of the pairs are reversed
- $\pi_1 (R)$ - Projection on the first coordinate of a binary relation R. So we return all of the pairs where $a$ is the first component
- R; D - Relative Product. R is a relation, D is a set. The set of pairs where the second component is in the set D

## Arc-consistency
![[Pasted image 20221015234105.png]]
if $a$ is in the domain of possible solutions for the first component but there isn't a $b$ that's in the valid domain such that there's a relationship between $a$ and $b$ then we can remove it from the domain. It's pointless keeping $a$ in the domain because it will never be used in a solution.
![[Pasted image 20221015234918.png]]
- So a constraint network is arc-consistent if for all elements in a domain, it has a relation with at least one other elements in a second domain
- revise(i,j) makes elements in i and j arc-consistent
![[Pasted image 20221016112107.png]]
![[Pasted image 20221016112256.png]]
![[Pasted image 20221016113033.png]]
__Directional arc-consistency__ is weaker than full arc-consistency but still just as useful in practice


![[Pasted image 20221016113648.png]]
- In the undirected graph the edges have no direction
- Width in a directed constraint graph is the maximum number of edges going __into__ a vertex
- Here is an example tree:![[Pasted image 20221016114101.png]]
- Notice that in this tree the vertices correspond to variables rather than assignments to variables from previous examples
	- Therefore it is much smaller than the search graphs we saw before
- The width here is 1 because the maximum number of edges going into a vertex is 1
- If the [CN](CN) is arc-consistent and if its constraint graph is a tree then we can be sure of getting a solution
	- Pick a value from the domain for the starting variable, then for a variable connected by an edge, so on and so forth until you have values for all variables\[__NEED TO VERIFY IF WE FILL OUT ALL VARIABLES OR JUST A SINGLE BRANCH__\]
		- For example we can pick an assignment for x1, then x2 then x5 and this will be valid within the constraints
	- We don't need to backtrack
- This does not apply for non trees (width != 1) even if arc-consistent![[Pasted image 20221016114726.png]]
- ![[Pasted image 20221016114954.png]]
	- Here we can assign values to x1, x2, x3 within the constraints but we can't assign x4 with certainty that we're not breaking any constraints
	- This brings us to a second form of Constraint Propagation:

## Directional path-consistency
![[Pasted image 20221016115511.png]]
- Just like directed arc-consistency except that we require pairs of assigned values be extendable by one step within the constraints of the network
![[Pasted image 20221016122206.png]]
![[Pasted image 20221016122634.png]]
- __CORRECTION__ If $N$ is strongly k+1-consistent, then it has a solution
- The ordering of variables changes the width, of course we aim for minimum width

Enforcing directional k-consistency becomes expensive as k grows, one workaround is __cycle cut-set__
![[Pasted image 20221016123456.png]]
- We simply removes cycles in the undirected representation of the graph
- After this we guess all possible values (exhaustive search), which isn't too difficult if the cycle cut-set is small
	- For each guess we adjust the remaining CSP
- Finding a minimal cycle cut-set is difficult but algorithms exist to do this
- We want to avoid blink search

### Alternative approach
![[Pasted image 20221016124220.png]]
- __CORRECTION__ bottom point: for all v in V (not v in W)
- The width is the maximum number of vertices in a node - 1
- Illustration:![[Pasted image 20221016125054.png]]
- So each vertex that has en edge to another vertex must appear in the same 'bag'
	- For example there's an edge between u and x; there is a corresponding bag {u, w, x} which contains both u and x
- Every vertex is represented in a bag
- Every vertex has a contiguous path between bags.
	- For example the bags containing u are all connected, there aren't any bags inbetween without a u
- We can see here the width is 2 because each bag has 3 vertices and the with is that - 1
- An acyclic undirected graph (no cycles) has tree width 1
- A higher tree width means its more cyclic
- If the original constraint graph is strongly 3-consistent (k-consistent generally) then we can work our way down the tree assigning values to variables and obtain a solution to the CSP

### Summary
We can always solve CSPs by search. But we want to avoid it because search is expensive. Constraint Propagation cuts down the search space, by analyzing the structure of the problem.

# Backjumping
Imagine a situation: ![[Pasted image 20221016133639.png]]
where we assign x1 to b1, x2 to b4 and then we get down to x3 and try and assign it and fail to meet the constraints.
- The problem might be that the value given to x1 at the start doesn't allow x3 to be assigned to any values in its domain.
- In this case there's no point in backtracking one step and exploring different values of x2
- We need to do a backjump where we jump all the way back to the last safe node
- ![[Pasted image 20221016133939.png]]
- There are many backjumping algorithms

### Gasching backjumping
![[Pasted image 20221016134136.png]]
![[Pasted image 20221016134336.png]]
- Consistency Checking:
	- Check the assignment xi = a first against x1 = a1 then x1 = a1, x2 = a2 etc up to x1 = a1 ... xk = ak
	- We break off if and when we violate a constraint
	- L(i) records the largest value of k for all of the values of $a$ that have been rejected so far when the algorithm returns
		- So L(i) is the shortest possible prefix of the current assignment required to show the inconsistency of all values ejected from the working domain so far.
		- If we return null and L(i) = k then the current assignment for xi...xk has no chance of yielding a solution and will fail for any assignment of xi
![[Pasted image 20221016135428.png]]
So if xi is null then the current previous variables don't allow for a consistent answer for xi, and thus we need to set i to L(i) which was the previous point there was consistency (I think)
