
### Top-Down Parsing
A way of constructing a valid parse tree from a sentence from constructing a tree from the grammar.

This is generally how humans construct a parse tree, looking at the grammar and the sentence and then choosing the path of the grammar that will lead to the sentence.

It is harder for computers to do as they don't have the intuition we have. Instead they employ backtracking, this can lead to infinite loops though.

In order to have efficient, backtrack free top down parsing we must ensure that the ==grammar isn't left-recursive==.

#### Left-Recursion
A left-recursive grammar is one that has a derivation which has a non terminal symbol on the left side like A => Aa

Eliminating Left recursion can be done in many cases by creating a new non terminal symbol like so:
![[Pasted image 20230403144229.png]]

#### Lookahead
In order to make parsing backtrack free we need to be able to look at the sentence in order to inform the choice in the grammar derivation.

##### LLB(1) Property
![[Pasted image 20230403144905.png]]

![[Pasted image 20230403144931.png]]

#### Pros
- Fast
- Good locality
- Simple
- Good error handling

#### Cons
- Hand coded
- High Maintenance
- Only suitable for simple languages

### Bottom-Up Parsing
More powerful than [[#Top-Down Parsing]], can lead to automation.

There are multiple algorithms for achieving bottom-up parsing such as LR(1), there are also other alternatives like LALR(1) and SLR(1) that produce smaller tables at the expense of larger space requirements.

#### LR(1)
This works by shifting the leftmost term in a sentence onto a stack and then choosing whether to shift another term or reduce what's currently on the stack to something else by referring to the CFG. This by itself isn't sufficient as there might be occasions when there's a choice as to whether we should shift or reduce, or choose between 2 different reduces. This is worked around by adding extra state information after each symbol in the stack
![[Pasted image 20230406121148.png]]

##### Skeleton
![[Pasted image 20230406120714.png]]

##### Example
![[Pasted image 20230406120623.png]]

##### Pros of LR(1)
- Fast
- Deterministic languages
- Automatable

##### Cons of LR(1)
- Large working sets
- Poor error messages


