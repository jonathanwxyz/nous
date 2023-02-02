### What is it?
- An [[Abstract DataType (ADT)]]
#### API
- `add(x)` - Creates a new set with x
- `find(x)` - Find the set that contains x
- `union(x,y)` - Merge the sets that contain x and y

### Implementations
Many ways to implement with varying complexities

#### Array or HashMap
![[Pasted image 20230122120443.png]]
- Key/Index is the item
- Value is the set
- Union(x,y):
	- Find all items within the x set and change the set to the y set
##### Complexities
- Find - $O(1)$
- Union - $O(n)$
- So Find is efficient but Union leaves something to be desired
#### Rooted Trees
![[Pasted image 20230122120820.png]]
Items are joined in a set if they have the same root to the tree.
##### Complexity
- Find - $O(n)$
- Union - Find + $O(1)$
#### Rooted Trees with Path Compression
Different forms of Path Compression
- Path Compression
	- ![[Pasted image 20230122121213.png]]
	- Must do 2 passes of the tree to do this compression
	- It leaves a very shallow tree which makes `find` very efficient
```python
 function Find(x) is
    root := x
    while root.parent ≠ root do
        root := root.parent
    end while

    while x.parent ≠ root do
        parent := x.parent
        x.parent := root
        x := parent
    end while

    return root
end function
```
- Path Splitting
	- ![[Pasted image 20230122121225.png]]
	- Connect each node to its grandparent
	- Done in one pass
```python
function Find(x) is
    while x.parent ≠ x do
        (x, x.parent) := (x.parent, x.parent.parent)
    end while
    return x
end function
```
- Path Halving
	- ![[Pasted image 20230122121239.png]]
	- Connects every other node to its grandparent
	- Done in one pass
```python
function Find(x) is
    while x.parent ≠ x do
        x.parent := x.parent.parent
        x := x.parent
    end while
    return x
end function
```