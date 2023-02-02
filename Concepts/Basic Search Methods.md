# First See
- [[Depth-First Search]]
- [[Breadth-First Search]]

# Cost
We often want to find a **least cost** solution. For example navigating between towns we might want the lowest distance traveled.
- We assume each action has a (non-negative) cost.
	-  Hence every node $\nu$ has a cost-so-far $C(\nu)$
- Assume that each situation has a (non-negative) **lower bound** on cost of achieving the goals.
	- Hence, every node $\nu$ has under-estimate of remaining cost $U(\nu)$
- There are two basic algorithms for traversing trees with cost: **branch-and-bound** and __A*__
- ![[Pasted image 20221011134255.png]]
	- Abandoning $\nu$ in this case means we don't need to explore the branch below (coloured red)

## Branch-and-bound Search
[[Branch-And-Bound]]

## A* Search
[[A* Search]]