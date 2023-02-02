
![[Pasted image 20221011135408.png]]
In these games both players know the entire state of the board with no uncertainty

These games can be represented by a tree where the rows alternate in who's turn it is to play (In this case, black and white). Playing these games can be seen as an adversarial search problem
![[Pasted image 20221011135553.png]]
We assume the rules of the game prevent it from going on forever, thus the tree is finite. At the end of the tree there will be leaves.

![[Pasted image 20221011135715.png]]
- Winning position of white: value = $\infty$
- Winning position of black: value = $-\infty$
- Draw: value = 0

![[Pasted image 20221011140753.png]]
maximizing node refers to nodes where the AI is taking its turn (e.g the AI might be playing as white) and because the winning position for white has a high value it is trying to maximise its points.
A minimizing node is for when the AI is trying to estimate which moves the enemy will take by assuming the enemy will take the best option available to them by minimizing their value as that is where their winning position is.

chess has about 10^120 nodes which is too large to be able to evaluate all positions
In this case we need a static evaluation function that will return for each board position the outcomes for a given player. So we can terminate the search of the tree at any point with a static evaluation at the end of the tree
![[Pasted image 20221011141445.png]]
We see here white has an advantage here, the static evaluation function will return a high value for white

![[Pasted image 20221011141550.png]]
This function searches the tree to a given depth
If we're at the limit of the search we return a numerical value for the static value of a node. We do this recursively so at a given depth we will find the best move to get to get the best score at that depth of the game

![[Pasted image 20221011142339.png]]
This returns the next move which should be taken

### Reducing unnecessary processing
![[Pasted image 20221011143156.png]]
Black - Minimizing nodes
White - Maximizing nodes

The boxes round the leaves at the bottom represent where a static evaluation function have been called
White knows that black will always pick the paths that lead to the lowest valuation, and black knows that white will always pick the paths that lead to the highest valuation.
Knowing this we don't need to calculate every single node.

For example we can see an incomplete branch on the left side (with 1 being the only one calculated). When it is white's turn there's no reason for it to pick this path because it knows that black will pick the move that gives it the valuation of 1. White has a better option which is to go down the middle branch which will net it the valuation of 2 (it won't get the valuation of 3 because black will pick the minimum of its options)

Another example is the right hand branch from the root node. From black's perspective at the root it can see the node with the valuations (3,4) coming off it which is better than any of the nodes on the left branch. So there's no point evaluating further because black knows that white will opt to go down that path regardless. So black would obviously take the move which takes it down the left side of the tree.

### Formally: $\alpha\beta$ pruning
![[Pasted image 20221011144302.png]]
![[Pasted image 20221011144934.png]]
![[Pasted image 20221011145108.png]]
This doesn't give superior results, it merely speeds things up!

![[Pasted image 20221011160832.png]]
