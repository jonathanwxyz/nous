#Algorithms-and-Data-Structures

### What is it?
A directed graph is a set of nodes (Vertices) $V$ and edges $E$ , where 𝐸 ⊆ 𝑉 × 𝑉.
![[Pasted image 20230131142348.png]]
V = { 1, 2, ..., 9 }
E = { (1, 2), (1, 3), (2, 4), (2, 5), (3, 6), (3, 7), (4, 8), (4, 9), (6, 5), (9, 2) }
	- First element of the tuple is 'from', second is 'to'
*Undirected Graphs*: edge pairs are not ordered (no arrows on visual representation)

==Path==: Sequence of nodes $u_1 ... u_n$, with $\forall i \in {1 ... n - 1}$ and $(u_i, u_{i+1}) \in E$
